+++
title = "NixOS made me Embrace my Lazyness"
thumbnail = "static/images/sloth_nix.png"
+++
{{ resize_image(path="./images/sloth_nix.png", width=400, height=400, op="fit_width") }}
---

# Table of Contents 

1. [Introduction](#introduction)
2. [The Sloth Proposal](#proposal)
3. [Conclusion](#conclusion)
4. [TODO/TOWRITE](#possible-posts)


## Introduction 

I started using NixOS out of actual necessity. I worked in a Lab at UEMG (Universidade do Estado de Minas Gerais), where i had 3 setups: my personal desktop at home, my laptop, and a VM on the Lab's stationary Workstation. I needed to work interchangeably, it was painful to keep track of packages and configurations for each one, and ditching the setup configuration to be the reason of an error was not that Trivial, so i had no much option besides NixOS, i didn't want to be always checking for missing packages, different home configurations, i just wanted to sync the setups and keep work going, NixOS was basically my only option.

### First Contact 

I installed nixOS on my computer and started to google how to get things working, i ended up installing a lot of packages with `nix-env -iA nixos.<package>`, wich is >not< the correct way, but i was figuring things out (and have since wiped the filesystems to clean up the mess).

But then, I understood how things were supposed to work, i just had to edit `configuration.nix` and rebuild my configuration, then, when i had to configure services, it got me to react with:

>" I just added this line, ran a rebuild and it all worked?"

I was surprised by how a single line would install the package, configure the service, sometimes change permissions for specific files, and everything would be done in a snap, it was shocking and enchanting at first glance.

Out of curiosity, i thought "how easy it is to change to another DE, completely different from the current one", considering GNOME and plasma, that have the GTK configuration, applications, and a lot of differences, it's common to have "trash" laying around when you try to switch between them, a lot of linux users just reinstall the root filesystem to change between them (and it's possible for the trash in the home filesystem to cause problems). 

Then, i changed my configuration, changing the option: 

`services.desktopManager.plasma6.enable = true` 

to: 

`services.desktopManager.gnome = true`

together with the `services.displayManager` option (check [NixOS options](https://search.nixos.org/options) on how to do the changes properly for your NixOS configuration and channel). 

When i logged out, the gdm screen already prompted me for a login, i've been using GNOME passionately on nixOS since. I was astonished about how clean and fast everything was, i had never imagined something like it on any other distro, dnf, from fedora, had a command for it, `dnf swap`, but it still left a lot of trash on your filesystem, so it was not a great experience migrating from one DE to another. 

I also had to install NixOS on my laptop, the last Arch Linux survivor, i just copied my config and ran a nixos-install, everything was in place, and i was ready to work on the projects i had to work at the time. I got shocked by how direct and quick everything was.


## The Ansible and/or Personal Scripting Alternative 

Before adopting NixOS, i considered using Ansible with another distro, there is a famous [Brazilian Youtuber](https://www.youtube.com/watch?v=vVBVZf9UtZY) who uses an Ansible-alike (using shellscripts) and "playbooks" for setting up the operating sytem, presenting a convincing case for it. However, when it came to my Arch Linux setup, I ultimately decided against it, since it was an "extra" solution on top of the OS, wich seemed less than ideal, since Ansible is not meant to be full-blown declarative opearting system like NixOS, and i didn't want to deal with testing it on clean installs, or having a problem with a shellscript, wich i cannot just change and rebuild to create a new generation (their changes in the filesystem are permanent), files that may be on a different place than what i have thought when writing the shellscript, something i copied from another script made for another distro, yada yada. The whole approach didn't seem appealing.

### How I Ended Up Sticking with NixOS After Leaving the Lab

I left the lab, but i was already in love with how NixOS works. I didn't have to activate services, i could insert tons of services into my configuration and just do a nixos-rebuild, everything was configured without any further intervention, i would have to consult the Arch Wiki to configure the user sockets for PipeWire, on NixOS, i just ran a rebuild and audio was working perfectly, with a single command and no headaches, i had functional Wi-Fi, audio, dhcp, disk automounting (udisks), Bluetooth and a DE to work, i could not imagine such a thing on Arch, were i was before.

## Proposal

NixOS is the sloths' operating system, it's great if you do not want to lose time with your OS. 

Most people think that NixOS is a system for those who want to babysit their operating system, spend their day configuring stuff, i'm here to propose that it's actually a great system for people wanting the opposite, to get things going quickly and easily. I fall into that second camp. My frustation with Canonical forcing Snaps on Ubuntu led me to Arch and now i can't imagine leaving NixOSn not even for a return to an ideal "Ubuntu", with tons of changes to the current state. 

### Example 1: Ollama/Aider simple and direct setup

Settings up Ollama is as simple as adding it to the services in your configuration.nix, including the models you want, and then running a rebuild. Afterwards, the models are downloaded and ready to be accessed locally. You can just copy and paste the code from the documentation, but i recommend organizing this withing your configuration.nix for a cleaner and easier file/config. 

Mine goes as follows:

As it shows in the `ollama ps` stdout, it's using only the gpu, working fine with my amd GPU and the open-source driver. The configuration in emacs is as simple as: 

``` 
(use-package aidermacs
  :bind (("C-c a" . aidermacs-transient-menu))
  :custom
  ; See the Configuration section below
  (aidermacs-default-chat-mode 'architect)
  (aidermacs-default-model "ollama_chat/llama3.1:latest"))
```
Which is just an adaptation of the copy-and-paste from the aidermacs documentation

Here is an example of it working with a simple FastAPI file containing a Pydantic (an external library) class: 


{{ resize_image(path="./images/aider_emacs.png", width=400, height=400, op="fit_width") }}

This, combined with the pop-up documentation that appears right when i hover over the _BaseModel_ statement, creates a powerful and comfortable setup.

### Example 2: Podman as a Docker Backend

When looking for how to configure Podman on NixOS, you will see this configuration snippet (probably not formatted like the snippet bellow): 

```
  virtualisation = {
       podman = {
          enable = true;
          dockerCompat = true;
       }; 
```

If you search for the virtualisation.podman.dockerCompat nixOS option, you will see a link a for a *default.nix* file, for convenience, it's [here](https://github.com/NixOS/nixpkgs/blob/nixos-25.05/nixos/modules/virtualisation/podman/default.nix).

This simple option implements a lot of configuration that people on other distributions would typically have to do manually to get everything working rootless. Since i'm lazy when it comes to tweak operating systems, i really appreciate the Nix way of doing it, i add a line and a whole complex configuration is done for me based on the file i edited before.

### Final example, the swiss army knife for zsh

The earlier Brazilian youtuber mentioned has his shell script for configuring zoxide, oh-my-zsh, specific zsh features, and scripts may differ for each distro. Also, there are aliases to consider, which you would have to set up all over again. Here, i just create the snippet and the zsh is already configured in any machine i want, 


```
       zsh = { 
          enable = true; 
	  enableCompletion = true; 
	  autosuggestion.enable = true; 
	  syntaxHighlighting.enable = true;
	  shellAliases = { 
	     enterDev = "nix-shell nix/shell.nix";
	     update = "sudo nixos-rebuild switch --upgrade";
	     clean = "sudo nix-collect-garbage -d";
	     cd = "z"; 
	  };
	  history = { 
	      path = "/home/lemos/.zsh/history";
	  };
	  oh-my-zsh = {
	      enable = true; 
	      plugins = ["git"];
	      theme = "afowler";
	  };
```

This snippet can be easily copied and shared with another user on your system, or with a friend who is just starting to configure their Home Manager setup on NixOS

## Conclusion

Basically, my whole point since the beginning is: NixOS does not require much work to get going (as most people think), yes, there is a learning curve, yes, you do need some time to get used to the "Nix"(tm) way of doing things.

And, if we are to be honest, we need to recognize switching to Linux itself has a learning curve on it's own, and we all undermine how much time we spent with this initial proccess. 

But after the first dive, nix actually makes it easier to manage your setup, since i got my system going, i spend no daily time taking care of the system, i am never anxious about updates, knowing that a previous a generation has my back, complex tasks, like getting a rootless Podman backend to work with Docker commands, were handled with a single configuration option, the docs for getting ollama with the amdgpu open-source driver did leave me a bit upset, looking like my RX6600 would be painful and need tons of specific configurations, instead, on NixOS it took just one snippet, and everyting was in place. I can't imagine living without that kind of comfort anymore.

## Possible Posts

There's more stuff i can and would like to write on my current setup, such as my gaming `specialisation`, which is a SteamOS-like configuration that inspired me to get back into PC gaming.

The flakes' issue, and why i still didn't migrate my configuration (and why every Nix-focused online group will have a lot of people telling you to do so)

Firebase/Google's Low-Code platform and how they use Nix into their environments



