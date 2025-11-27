+++
title = "Junior's Strangelove or: How I Learned to Stop Worrying and Love Front-End development"
thumbnail = "static/images/sloth_nix.png"
+++
{{ resize_image(path="./images/strangelove.jpg", width=400, height=400, op="fit_width") }}
---

# Table of Contents 

1. [Introduction](#introduction)
2. [The VueJS Lands](#the-vuejs-lands)
3. [Meeting ui.shadcn](#shadcn-components)
4. [Conclusion](#conclusion)

## Introduction

I got into programming with PHP, C and some Pascal (yeah, doesn't fit my age, i was reading a book i took from a library), When i was still young, so i wasn't much into front-end programming to begin with, in my mind, front-end was summarized into html/css and jquery, little did i know. 

Front-end development always seemed like a frustrating mess. Flexbox, for instance, was a nightmare. I spent countless hours debugging why a box overlapped another, or why resizing the screen broke my entire layout.

Nothing attracted me into front-end and i had the stigma that front-end was boring, mostly delegated to designers and something a "true hardcore programmer" (yeah, shame on me for thinking like that at the time) would never touch. React, Typescript, TailwindCss was something to shame and blame for all problems in the modern web, front-end was about "changing colors, shapes and texts, while backend was about "performance, databases, http, APIs", this is far from being the reality that i now know. 

## The VueJS lands

The open-source community really loves Vue, and I got caught up in the hype. It was exciting to work with a framework that felt more 'HTML-like,' something familiar to me. It was a comfort zone for someone who wasn’t ready to dive into full-fledged front-end development, but still wanted to keep a project going with a stable and known framework. I got into developing with it, but i didnt actually learn something, i was just doing html with some scripts on it. My axios code was messy. Error handling was not a thing. Alerts? Good statem management? Mobile-friendly UIs? Neither. 

FrontEnd was easy to "bootstrap", but not easy to actually get stuff done, when i needed to work with it, do actual code that did matter, i hated it and spent too much time when i actually had to do an important task. 

Something had to change, i had to get stuff done and change this reality wich was not sustainable. And the whole fault was on me, not on vue, since it's actually a full-fledge option to use consolidated frameworks, libraries, the DaisyUI components, etc. 

### Typescript, Axios, pinia/zustand

Modern front-end development requires attention to detail, especially with aspects that many beginners overlook. In large projects, interfaces are carefully defined for each case. The code should avoid using :any for anything (like most llms output js code) and relying too much on type-infer. A code reviewer may not be as lenient with your approach, so it’s important to adopt best practices from the start. Axios requires knowing how to read API documentation and actually consume it, if you're too confident with the knowledge from a crash course on html/js/css, this will surely be a hassle. Pinia (for vue) and Zustand (for react) are mandatory for real-world applications and development. This will lead you into state management, wich is an important part of front-end development and actually needs to be done properly, or you will get tons of components not rendering, messy data, "autofilled" inputs that shouldn't be there, etc. This was my first hassle when developing with vue having 0 knowledge on front-end development, so this led me to actually do something about my situation. 

## shadcn Components

A friend at college introduced me to ui.shadcn, i could get a front-end running with small `.tsx` files. I just had to do basic changes using tailwindcss, running through ui.shadcn docs and managing axios/state-management, etc. It was the way for breaking the first barrier i had with front-end development, the time developing interfaces and keeping a concise design and placement with tailwindcss, all i had to do was `pnpm dlx shadcn@latest add <component>`, and then import the component into the page i wanted it to appear. The design came with the theme provided through ui.shadcn and the visuals kept consistent through the application without further changes. And everything looked awesome for the clients i had. 

This left me with the task of giving it some "extra spice" so everything keeps responsible in another screen/device such as a mobile interface, keeping the axios request correctly and with proper error handling, and adding `useEffect()` functions, handling state management, i actually discovered what was front-end development in pratice, instead of copying opinions from people on the internet without knowing the reality when you're actually coding.

### FrontEnd real-world issues

I was finally handling real programming tasks: making HTTP requests, defining types, creating interfaces, writing functions, and dealing with logic errors. It felt great to see the results: organized code, proper type assertions, working HTTP methods, and modularized code. For the first time, I was truly programming a front-end application

All of this work actually needed thinking, and "vibe-coding" stuff would lead to a unreadable code in hours. Unless you're really skilled with prompts and AIs, chances are high that code produce will be verbose, infering `:any` for everything, not modularizing the code, etc. This will become an avalanche and lead to a dead project that cannot be maintained without requiring more work than a rewrite would take. 

### AI and Copilot Code-Completion

With the "AI Revolution", a new workflow came for most of us, now, AI agents, LLMs decide a great part of our code, i wasn't an exception, a great part of my front-end code was initally driven by AI, an axios instance was almost instantly created writing axiosInstance = . This already created the whole function for me. 

Copilot's code completion basically can turn what would've taken 5 hours into a 10 minutes task with a robot shakings hands with you at the park. It was able to create axios request with consistent identation (despite inserting too much console.logs :^) ). Templates? Claude and emmet made reusable components in a blink, making them easy to import and `.map`. Insert a lambda function into your input, button, select and everything was possible, easy and simple, while ui.shadcn left ready the "heavy lifting" of ui consistency, providing responsive objects, dark-light mode handling, etc. The interface appearance became secondary and UX, API compliance and other real-world issues became the relevant thing.

And now? AntiGravity got even better when getting everything strongly-typed, since the agent knows exactly how it should threat data and handle requests, maps, etc. No more `undefined`-hell :^). 

## Conclusion

Throughout all this proccess, i came out a different professional, truly, removing stigmas and caring about facts and learning with the hands on code got me into thinking with less pation over technical stuff and slowly moving into a practical mindset that actually cares about the techinal needs, and ignores whatever "looks coll" on social platforms (xD). I learned that front-end development involves more than just layouts, it includes essential topics like state management, authentication, handling files with Base64 encoding, writing lambdas for specific tasks, and creating consistent and modularized code.

Using windows? never! Typescript? This is not something for true programmers! React? It's an overhyped framework. All of this mindset has no actual benefit, you're limiting yourself to a bubble that you will eventually have to pop while searching for a job, "boring" technology matters. It gets stuff done, it does not make "cool" technology useless and non-worthy, but it is what the market uses, learning how to deal with it expand your horizons, and you can "merge" the knowledges from cool technology (like FP-focused languages), into the "Boring technology" you have at your average consulting enterprise. Less passion, more reason.

God Bless.
