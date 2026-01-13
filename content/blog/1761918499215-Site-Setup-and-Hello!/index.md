---
title: "AI-Free Object Tracking or Bust! | AIO Gimbal Controller Devlog 1"
date: 2025-10-31
draft: false
description: "The First Devlog for my AIO Gimbal Controller. More to come soon... :eyes:"
summary: "The First Devlog for my AIO Gimbal Controller. More to come soon... :eyes:"
tags: ["first post", "setup", "original", "initial post", "start"]
---

## Introduction

Howdy Reader! 

Welcome to my first devlog for my AIO Gimbal Controller.<br>
I'm mostly creating these devlogs to help myself with keeping track of various project details and avoid repeating my mistakes, but they might prove entertaining or informative to someone else down the line eventually.

If you haven't read the project brief, I've done a basic project analysis you can view [here.](/AIO-Gimbal-Controller/)

The basic gist is that I want a complete, all-in-one gimbal solution that can be retrofitted to any drone (with an appropriate MTOW and a large enough form factor.) The two control modes I'm looking for are: manual control via a thumbstick, and automatic tracking via a secondary device on a subject. 

## Initial Prototype

## Justifications

My initial design decisions have largely been informed by one factor: cost. I've chosen components that are cheap, simple, or recovered from tech I already have. Even in spite of this, the current setup cost has already exceeded $100AUD, and so I wouldn't recommend getting into a project similar to this unless you have a decent understanding of microcontroller tech and can avoid the pitfalls I fell into. 

### Why STM32?
For my microcontroller, I've decided to go with a Nucleo32 MCU. My justification for this decision are two-fold:<br>
1. it has far better CPU, clock speed, RAM and firmware size than similarly sized Arduinos such as the Arduino Nano, (and since this project needs to be able to fit into a user's pocket MCU size matters) and;<br>
2. I'm familiar with them and already had several laying around.

RE: the second justification, given that I'm receiving no financial help with this project and am developing it on my own time, money and passion, I see every cent saved as invaluable. One of the many things I've learnt during development of my prototype has been that whilst it's possible to spend hours speccing a component to within your project requirements, sometimes simplicity and money win out. In the interest of shortening my R&D time and saving money by avoiding purchasing respecced components, cheap beats optimal every time.

HAL coding is still painful, and made no easier by STM32CubeIDE's cantankerous attitude to basic requests, but I always find that limitations in projects like this only make development more chaotic and fun. STM32 may not be as foolproof as Arduino but through developing my initial prototype I've found that a neat side effect of having to code from the ground up is that I've gained a top-to-bottom understanding of my implementation.

### Why that power supply? 
Looking at my solution you may have noticed a particularly ugly power regulator unit. This is, as I'm sure many hobbyists could recognise, the power regulator meant to fit on an Arduino board, with pin spacing specifically for the dupont pins on Uno-/Zero-form-factor boards. <br>
Why use a massive power regulator that still only provides 600mA output and has features that are completely unnecessary for this project?<br>
I'm familair with them and already had several laying around.<br>
Again, familiarity means less time doubting the regulator's quality; already having several available means no down-time waiting for components to arrive; redundant feature means less chance of having to respecc later on should my requirements change. <br>
Of course, if I was designing for a commerical product likely to be used outside of my film projects or MUAS' flight days, I would eventually move from these R&D-grade components to better specced, more specialised components, in order to bring both cost and size down. 

### Why the rest of those components?
For all other components, they're easy enough to justify:

- My thumbstick is a simple 2-potentiometer gaming controller thumbstick. Whilst this is technically less reliable and lower resolution than hall-effect-based thumbsticks, it makes more sense given my space restrictions and the filtering that's already going to be applied to manual camera control inputs.

- My barometer, magnetometer and GPS are all "Arduino-friendly" components built to be interfaced with breadboards and Arduinos. These offer great performance without me having to spend precious development time designing my own sensor logic. So far, I'm pretty blown away by the resolution of each of these components given that their total cost is less than $35AUD

- My radios are pairs of 915MHz 3DR SiK Radios. When it comes to UART communications, these are incredibly simple, compact, and designed for drone use, making them especially resilient to damage and ESC-frequency-range interference.

## Where to now?
The next step will be to implement true data fusion between my GPS, barometer and magnetometer to create a high-quality picture of the drone's true position, both relative to the Earth and the sister device. With this I'll be able to get automatic camera tracking running and put those telemetry sensors to use, since I get the sense they're starting to feel left out.