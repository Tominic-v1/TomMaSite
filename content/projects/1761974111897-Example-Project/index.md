---
title: "All-in-One High-Level Gimbal Controller"
url: "/AIO-Gimbal-Controller/"
date: 2026-01-13
draft: false
description: "A Specialized Solution for Automatic Object Tracking and Remote Gimbal Control, All-in-One Package."
tags: ["Gimbal", "Drones", "Multirotors", "Filming", "Hobby", "Project"]
---
**A Specialized Solution for Automatic Object Tracking and Remote Gimbal Control with an All-in-One Package.**

# Abstract
Traditional camera-drone solutions are designed to function within the existing drone's avionics ecosystem, requiring for changes to the drone's design and architecture to implement. With this solution, the objective is to eliminate this dependency and create a completely all-in-one gimbal package, including manual control of the gimbal's attitude via a ground operator, and automatic visual tracking of a sister device.

This device is to be built on top of an existing gimbal/gimbal-controller pair and is only designed for high-level control of the gimbal's attitude. The creation of a new gimbal and gimbal controller, capable of IMU measurements and camera stabilisation, falls outside the scope of this project. 

With this complete solution, one should be able to place nearly any gimbal/gimbal-controller pair and this device onto any drone (given an adequate MTOW), and capture clear, high-quality footage without significant camera operation experience. 

The addition of automatic tracking via the inclusion of spatial positioning technologies could potentially eliminate the need for a dedicated camera operator. By gathering the position of both the gimbal-side device and sister device, the gimbal can be told to point in the direction of the sister device at all times, allowing for automated object tracking without human intervention.

# Background
While flying my RC plane at my local airfield recently, I had to imagine what the view from a camera drone tracking my plane would be. The problem was that I didn't currently have any drones capable of supporting and controlling a gimbal, and I didn't have a hand free to control the camera regardless. 

I figured that a simple, AIO retrofit gimbal controller would be the only solution, one that included automatic object tracking via a sister device on the video's subject. 

I've seen a fair share of drone flights, both at MUAS and in my own time. Other obstacles I knew I needed to overcome included the difficulty of tracking objects using only low-quality FPV feeds, especially when the object was in a noisy environment, concealed by foliage, or in front of the sun. These issues served to further push me towards the solution I had been imagining.

AI-powered object tracking, whilst significantly more robust than it used to be, still has limitations when there are multiple aircraft flying in a single airspace, and struggle if the subject is concealed by foliage or is in front of the sun.

>![Example of a difficult scene for traditional drone photography. via u/akotski1338](/ExampleImage1.jpeg)
>*via u/akotski1338*

# Problem Analysis
## Objective
To create a solution capable of attaching to existing drones without changes to that drone's architecture, which allows guided manual and automatic gimbal control, eliminating the need for a highly skilled camera operator to capture high-quality aerial footage. The need for a drone pilot cannot yet be (legally) eliminated, the need for a camera operator should be completely eliminated by the device's autonomous mode.

## Functions
Primary Functions
- Control gimbal attitude
- Automatically track its sister device
- Allow manual gimbal control via the sister device

Secondary Functions
- Identify the device's spatial position relative to its sister device
- Communicate wirelessly via long-range radio signal
- Be powered by a completely independent power system and battery

## Restrictions

### Financial

The initial solution may take several iterations to develop and will be built on student-level experience in microcontroller programming. As such it's important to consider the importance of reducing development costs in the earliest stages of product development, as large investments may prove unnecessary with additional learnings. 

### Experience

As mentioned under the Objective heading above, this solution must be designed to be usable without significant training or explanation. Its design, including its housing's form factor and status indicators, must be self-explanatory to the untrained eye.

### Performance 

For gimbal control, measurements and calculations will need to be rapid and clean. The selected microcontroller and peripherals must be capable of high-speed communication and acquisition of subjects in order for the recording quality to be a significant increase from the average user. 

<br>

# To Be Continued...
