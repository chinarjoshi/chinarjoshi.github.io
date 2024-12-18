---
layout: post
title: Save an hour of battery by dimming the screen when you look away
# subtitle: Optimizing local vision through compression and sleep
subtitle: Defeating perceived latency using tiny models and Pareto-navigation
metadata: (011)
permalink: /attention/
category: desktop
type: solution
---

Intel, AMD, and recently Apple have optimized CPU microarchitectures to the point that they do everything at the cost of nothing. Desktop CPUs are the pickleball players who effortlessly play with their left hand while talking a call in their other, while I/O devices are the people struggling on the other side of the court. The display is the sluggish player that is always one step behind and needs 30% of the resources, no matter how hard they train. We humans always ask for bigger displays, denser resolutions, faster refresh rates, and all three of these are counter to battery efficiency. At least CPU can cheat by deepening its pipeline, predicting branches to even more perfect degrees, issuing more instructions in parallel, and even radically changing its architecture to support new workloads. But there is a fundamental difference between processor and I/O: CPU must always be correct and maximally efficient, while I/O must only be as correct and efficient as the human on the other side. 

Personally, I do not operate at 5 billion instructions a second, so even if my screen displays the wrong content +10% of the time in exchange for +20% lifetime, that is a net positive change. This was the concept behind auto-dimming screens, which use a timeout to guess whether or not you're watching the display. However, we can approximate this boolean much more directly by modeling head pose with the camera. For years this was a laughably heavyweight approach, like using a sledgehammer to crack open a peanut. But, by employing recent advances in small models (knowledge distillation and quantization) and efficient daemon application design (blocking syscalls on devices), I hypothesize we can improve upon the auto-dimming approach to dynamically navigate the Pareto-frontier of the screen brightness vs attention likelihood plot.

## **DISCLAIMER:** Most of this rough draft was written by GPT-4 given my ideas. As such, the content is incomplete and factually ungrounded. Please check back in 2 weeks for the full version now that I have free time.

### Model Selection and Optimization:

We start by employing a lightweight binary classification model designed to ascertain one thing: Is the user looking at the screen? This reduces the complexity found in multi-class gaze tracking and engagement measurement, drastically cutting down the computational cost.To further enhance efficiency, we employ model quantization techniques, reducing the precision of the numerical calculations from floating point to integers, which accelerates computation speeds and lowers power consumption.

### Kernel-Level Optimizations:

Utilizing kernel tricks is crucial for minimizing the impact on system resources. By leveraging inotify, a Linux kernel subsystem, the system monitors /dev/input/eventX files representing user input devices. This mechanism uses interrupts rather than polling, significantly reducing CPU load as it waits for specific file changes to signal user activity.For times when the user's focus shifts frequently, we employ the select syscall. This syscall efficiently manages multiple file descriptors, sleeping until it detects input activity or a timeout occurs, ensuring that our monitoring process remains lightweight.
Given the non-blocking nature required, we integrate the select and poll syscalls to monitor user interactions. This allows our application to remain dormant until a significant event (like a change in the user's gaze) triggers it, thus conserving CPU cycles.In scenarios requiring immediate responsiveness, the application leverages multi-threading to handle input/output operations asynchronously. This parallel processing capability ensures that our application can perform intensive tasks without stalling the user interface.
Configurability and Modular Design:

My implementation is a program that takes pictures from the laptop camera and dims the screen if you're looking away for a user-defined amount of time. It uses a gaze estimation model tuned for edge-computing mobile devices, MobileGaze, that is trained on the GazeCapture dataset. Gaze estimation is a regression task that determines the x,y coordinates on the screen that the user is looking at. I present a new model, MobileAttention, that determines whether or not the user is looking at the screen, a simpler classification task.
The result is a model that is incredibly efficient, both in terms of speed and FLOPs. 

The pipeline is defined below:
 1. Take a picture from the laptop camera (OS specific)
 2. Use Haar Cascade to determine the facial area of interest
 3. Use Diibs algorithm to determine landmarks (eyes and face center)
 4. Crop the image around the landmarks
 5. Feed into MobileAttention model to classify
 6. Determine whether or not to dim the screen

The added complexity comes from batch operations into the network: A picture can be taken twice a second, and only processed every 5 seconds. If at any point in the sequence the user is looking away, then you can more accurately respect the timer defined by the user.

Another important consideration is ongoing learning. Using the feedback from the user to continue to improve the model. A successful dim is defined also by the user with a default of 3s. If the screen is dimmed for 3 seconds, then it was worthwhile. Otherwise, the model should not have dimmed the screen.

This system exemplifies how a seemingly small tweak—adjusting screen brightness based on attention—can lead to significant improvements in battery life and user experience. By embedding intelligent, context-aware capabilities into our devices, we can make them not only more efficient but also more intuitive to our needs.
