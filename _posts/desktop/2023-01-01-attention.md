---
layout: post
title: attention - extends your battery life by ~1hr by dimming screen when you're facing away
permalink: /attention/
category: desktop
type: solution
---

Did you know that 30-40% of your laptop battery goes to powering your screen?! If we get even a 20% decrease of the power requirement of the screen, for a standard 10-hour battery charge, you can expect to gain about *40 minutes* of battery life. Since we usually don't look at our screen even 80% of the time, this is a very feasible optimization to achieve. Thus, I attempt to solve this problem by greedily dimming the screen when it's not being utilized, which means no-one is looking at it.

This is a program that takes pictures from the laptop camera and dims the screen if you're looking away for a user-defined amount of time. It uses a gaze estimation model tuned for edge-computing mobile devices, MobileGaze, that is trained on the GazeCapture dataset. Gaze estimation is a regression task that determins the x,y coordinates on the screen that the user is looking at. I present a new model, MobileAttention, that determines whether or not the user is looking at the screen, a simpler classification task.
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
