---
layout: post
title: How To Make ChatGPT Write Quality Code
date: 2023-10-18
---

ChatGPT has elevated professionals in every field, yet I feel like programmers still aren't maximizing its utility. It has enabled everyone from solo programmers to massive teams to create useful, timeless software with ease. In this article, we'll delve into new best practices that will enable you to make the most out of ChatGPT for your coding projects.

## Provide All the Context Up Front, Then Reuse the Chat for the Whole Project

### The Currency of Context

GPT-3 writes correct code ~10% of the time, while GPT-4 does so ~90%. However, the code only matters if its right for you; incorrect assumptions often lead to more debugging time than writing it from scratch. In fact, currency of ChatGPT is **context**. The more context you can provide, the higher the utility you'll get in return. To optimize your project, start immediately by building a continuous chat with ChatGPT. 

### Shared Links as Snapshots

ChatGPT has an incredibly useful feature: a little button on the top to create a shared link. Keep this URL in the root of your repository, name it something like `CHAT`. These shared links are *snapshots*, perfectly compatible with Version Control Systems (VCS). This means unaquianted users cannot change history, but everyone can "chat with the project" on their own, and the repository maintainer can keep it updated with good queries. As a result, anyone with access to the repository can delve into the design philosophy and implementation details from the ground up.

## You Write the Test Cases, AI Does the Implementing

### The Beauty of Black Box Abstraction

Craft your test cases carefully, keeping in mind the public API and unit interactions. Then let ChatGPT implement the logic. This black-box approach forces you to think about what you really want from each unit of code, ensuring high quality and idiomatic code in the process.

### Defensive Programming and Unix Philosophy

[Should software be designed top-down or bottom-up](https://softwareengineering.stackexchange.com/questions/134633/is-is-preferable-to-design-top-down-or-bottom-up)? While there is no right answer, I believe the bottom-up approach more naturally fits this workflow. This means write independent, carefully tested method headers that can be implemented with a black-box. In this sense, stick to the Unix philosophy of doing one thing exceptionally well. Complex ideas and implementations stem from stitching together simple, effective ones. It helps to defensively program: assume the minimum needed when writing the header, and don't assume anything more than stated in the documentation when verifying the implementation.

## Write Good Documentation Early

### The Importance of Docstrings and READMEs

Start documenting early in the development process. Be it docstrings for your code or the README for your project, good documentation should make it trivial for chatGPT to work for you, and for other humans to understand how to use your software and what went wrong if something breaks.

### The User Experience

Good documentation minimizes the learning curve and makes troubleshooting easier. It embodies the philosophy that users should expend the minimum amount of effort to achieve their goals.

## Conclusion: Work Smarter, Not Harder

The trick isn't just to let AI blindly do the heavy lifting, but to complement human skills. Write your test cases carefully to define the boundaries of what you want to achieve, then let ChatGPT fill in the blanks. Document as you go along, not just for the sake of records but to make the development process easier and the end result more robust.

In the ever-changing world of programming, adopting rigorous LLM-powered workflows can save you time, improve code quality, and allow you to focus on complex problem-solving. After all, the best-designed programs are those that are the easiest to write and maintain.

## Thought-Provoking Idea

How will the incorporation of AI into software development change traditional roles within a development team. When we see a future where AIs are not just faceless tools, but integral team members contributing to code reviews, debugging, and even architecture design?