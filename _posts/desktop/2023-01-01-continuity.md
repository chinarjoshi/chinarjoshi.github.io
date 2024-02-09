---
layout: post
title: Search everything you've seen, said, or heard
permalink: /continuity/
category: desktop
type: solution
---
I forget things too quickly after they happen. I wish I lived in that episode of "Black Mirror" where a brain chip records your audiovisual senses and lets you rewatch your memories. But alas, the ubiquitous solution is to note-take the things you learn, which is fundamentally an *O(n)*, manual operation. I need an O(1) solution to this note-taking problem, a second brain if you will.

This problem falls into the space of personal data capture and management. Most tools feel like copycats of each other, but one recently stood out to me: *Rewind.ai*. It's a background app that captures and labels on-screen text and microphone input. Since practically everything we learn is now through our laptops, it captures everything. This is a functional, efficient implementation of a second brain! 
Small problem though, *it's extremely proprietary and only runs on Apple devices*. It only runs efficiently because Apple devices have efficient neural network processors and fast, developer-friendly AI libraries, and it's proprietary so it can charge you $20 a month.
This is actually not a big problem, because Rewind.ai doesn't do anything special that we can't do ourselves. Creating an open-source pipeline out of a language model, text-from-image model, and voice-to-text model, along with a native data capture program will give us the exact same thing, except we know exactly what's happening to our data!

# Introducing: `continuity`
