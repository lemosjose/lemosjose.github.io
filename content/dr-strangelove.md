+++
title = "Dr. StrangeLove: A Mea Culpa on Front-End development, or: The Confessions of a ex-Wannabe"
thumbnail = "static/images/sloth_nix.png"
date="2026-03-18"
+++
{{ resize_image(path="./images/strangelove.jpg", width=400, height=400, op="fit_width") }}
---

# Table of Contents 

1. [Introduction](#introduction)
2. [VueJS](#vuejs)
3. [shadcn](#component-libraries)
4. [Conclusion](#conclusion)

## Introduction

I got into programming with PHP, C and some Pascal (yeah, doesn't fit my age, i was reading a book i had taken from a library), When i was still young, so i wasn't very interested in front-end programming to begin with, in my mind, front-end was basically html/css and jquery, for some newcomers, this can be true for a while. 

Front-end development always seemed like a frustrating mess. Flexbox, for instance, was a nightmare. I won't even mention z-index. I spent countless hours debugging why a box overlapped another, or why resizing the screen broke my entire layout, and my literacy with computer science was minimal.

Nothing attracted me into front-end and i had the stigma that front-end was boring, mostly delegated to designers and something a "true hardcore programmer" (well, sadly, how the average wannabe looks a the topic) would never touch. React, Typescript, TailwindCss was something to shame and blame for all problems in the modern web, front-end was about "changing colors, shapes and texts, while backend was about "performance, databases, http, APIs", this is far from being the reality that i now know. And despite my hate for front-end (which was not a well-formed opinion, of-course), i didn't actually know Back-End, i just copied what memes and messagees in online chat groups would say about front-end development.

## VueJS

The open-source community really loves Vue, and I got caught up in the hype. Because i didn't know any better, i thought that vue was a "hyped-up Html", I wrote templates badly, and in the end, i was just structuring html, without requests, logic handling, composables,components, nothing, i was doing bad, messy code while telling myself I was learning front-end dev/architecture.

FrontEnd was easy to "bootstrap", but not easy to actually get stuff done if you don't know what you're doing, when i needed to work with it - on code that did matter, i hated it and spent too much time attacking minor issue while i actually had to do an important task. 

Something had to change, i had to get things done, now i had front-end as an actual responsability and change this reality, wich was not sustainable. And it was entirely my fault, not on Vue, since it's actually a mature ecosystem of frameworks, libraries and tools. AI/LLMs don't perform miracles when you don't even know how to instruct it. 

### Tooling

Modern front-end development requires attention to detail, especially with aspects that many beginners overlook. In large projects, interfaces may be carefully defined for each case, and there are enough functions (or hooks) so you cannot just leave them around your "html", like i did, you need an actual project: organizing files, keeping a clear structure, clear design, etc. Much of my approach to problems improved when i forced myself not to use type-infer, since this improved clarity and the efficiency of llms, while also forcing me to keep track of the architecture, types, hooks that used types/interfaces correctly, something i did not care about at the time the code was basically html on steroids. A code reviewer may not be as lenient with your approach, so it’s important to adopt best practices from the start. Using axios requires knowing how to read API documentation and actually consume it, if you're too confident with the knowledge from a crash course on html/js/css, this will surely be a hassle. Pinia (for vue) and Zustand (for react) are mandatory for real-world applications and development. This will lead you into state management, which is an important part of front-end development and actually needs to be done properly, or you will get tons of components not rendering, messy data, "autofilled" inputs that shouldn't be there, etc. PageSpeed will also not care about your feelings when the evaluation process runs, it may be really hard to get things tested without jest/vitest or e2e testing, a bad codebase will give you headaches for months if you don't understand what you're doing. This was my first hassle when developing with vue having 0 knowledge on front-end development, so this led me to actually do something about it. 

## Component Libraries

A friend at college (@eduumach on GitHub) introduced me to ui.shadcn, i could get a front-end running with small `.tsx` files. I just had to do basic changes using tailwindcss, running through ui.shadcn docs and managing axios/state-management, etc. It was the way for breaking the first barrier i had with front-end development, the time developing interfaces and keeping a concise design and placement with tailwindcss, all i had to do was `pnpm dlx shadcn@latest add <component>`, and then import the component into the page i wanted it to appear. The design came with the theme provided through ui.shadcn and the visuals kept consistent through the application without further changes. And everything looked awesome for the clients i had. 

This left me with the task of giving it some "extra spice" so everything keeps responsible in another screen/device such as a mobile interface, keeping the axios request correctly and with proper error handling, and adding `useEffect()` functions, handling state management, i actually discovered what was front-end development in pratice, instead of copying opinions from people on the internet without knowing the reality when you're actually coding. Now i had an organized codebase and could actually understand the project, prompt agents to produce structures based on the patterns i stated, things were flowing for the first time.

### FrontEnd real-world issues

All of this work actually required thinking, and "vibe-coding" things from scratch would lead to an unreadable codebase within hours. You cannot run a project based on "redo the whole application now, consider this error, make no mistakes", you need to know exactly what you want to fix, have a readable codebase..... AIs does make the job really easier, less stressful and they are really good at doing front-end work, but without a proper prompt, they are as lost as you are. 

### Agentic Coding

With a readable codebase, agents can make the job really faster, they already know your patterns, how often your code is commented, when not to do bullshit-ish `console.log` calls, they can actually be a robot that does "pair programming" with you, and as a real pair, code needs to be readable and clear. 

AntiGravity, Cursor are great tools, if you know how and when to use them, agents are not self-conscious, some codebases may need more attention to details, agents will ask for commands that maybe they don't know how harmful they are, with proper knowledge, they are a partner in code, not a partner in crime.

## Conclusion

Throughout all this process, i came out a different professional. By removing stigmas, focusing on facts, and learning through hands-on coding reduced emotional (and "hype-ish") bias in how i approach technical topics, moving torwards a practical mindset that actually cares about the techinal needs, and ignores whatever "looks cool" on social platforms and online memes. I learned that front-end development involves more than just visual candy, the project needs to be managed, code needs to be written with patterns and clarity in mind, agents do not go wild alone, a human prompted it's wildness, the front-end needs to meet performance metrics, consider UI/UX issues, interact with backend/workers, if a human does not understand the architecture, the agent becomes a wild bear scraping for food.

Despite the internet hate on topics, despite how "cool" things look when you don't actually work with them, focus should be on objective results, metrics and delivery, do not take stands you don't need to. 