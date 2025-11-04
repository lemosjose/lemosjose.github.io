+++
title = "Dr.Strangelovable or: How I Learned to Stop Worrying and Love Front-End development"
thumbnail = "static/images/sloth_nix.png"
+++
{{ resize_image(path="./images/sloth_nix.png", width=400, height=400, op="fit_width") }}
---

# Table of Contents 

1. [Introduction](#introduction)
2. [Meeting ui.shadcn](#ui.shadcn)
3. [Conclusion](#conclusion)
4. [TODO/TOWRITE](#possible-posts)

## Introduction

I got into programming with PHP, C and some Pascal (yeah, doesn't fit my age, i was reading a book i took from a library), When i was still young, so i wasn't much into front-end programming to begin with, in my mind, front-end was summarized into html/css and jquery, little did i know. 

Front-end always looked like a boring mess, flexbox? This was a headache that led me into hours and hours debugging why a box went over another and why changing the screen size broke my whole site.

Nothing attracted me into front-end and i had the stigma that front-end was boring, mostly delegated to designers and something a "true hardcore programmer" (yeah, shame on me for thinking like that at the time) would never touch. React, Typescript, TailwindCss was something to shame and blame for all problems in the modern web, front-end was about "changing colors, shapes and texts, while backend was about "performance, databases, http, APIs", this is far from being the reality that i now know. 

## The vue lands

## ui.shadcn and components reusage

A friend at college introduced me to ui.shadcn, i could get a front-end running with small `.tsx` files. I just had to do basic changes using tailwindcss, running through ui.shadcn docs and managing axios/state-management, etc. It was the way for breaking the first barrier i had with front-end development, the time developing interfaces and keeping a concise design and placement with tailwindcss, all i had to do was `pnpm dlx shadcn@latest add <component>`, and then import the component into the page i wanted it to appear. The design came with the theme provided through ui.shadcn and the visuals kept consistent through the application without further changes. And everything looked awesome for the clients i had. 

This left me with the task of giving it some "extra spice" so everything keeps responsible in another screen/device such as a mobile interface, keeping the axios request correctly and with proper error handling, and adding `useEffect()` functions, handling state management, i actually discovered what was front-end development in pratice, instead of copying opinions from people on the internet without knowing the reality when you're actually coding.

I was handling actual programming, http requests, types, interfaces, functions, dealing with logic errors, error handling, throwing exceptions, it was a great feeling

## Conclusion and Post-Code Notes

Throughout all this proccess, i came out a different professional, truly, removing stigmas and caring about facts and learning with the hands on code got me into thinking with less pation over technical stuff and slowly moving into a practical mindset that actually cares about the techinal needs, and ignores whatever "looks coll" on social platforms (xD)
