Engineering materials
====

This repository contains engineering materials of **AUMers02** self-driven vehicle's model participating in the WRO Future Engineers competition in the season 2025.

## Content

* `t-photos` contains 2 photos of the team (an official one and one funny photo with all team members)
* `v-photos` contains 6 photos of the vehicle (from every side, from top and bottom)
* `video` contains the video.md file with the link to a video where driving demonstration exists
* `schemes` contains one or several schematic diagrams in form of JPEG, PNG or PDF of the electromechanical components illustrating all the elements (electronic components and motors) used in the vehicle and how they connect to each other.
* `src` contains code of control software for all components which were programmed to participate in the competition
* `models` is for the files for models used by 3D printers, laser cutting machines and CNC machines to produce the vehicle elements. If there is nothing to add to this location, the directory can be removed.
* `other` is for other files which can be used to understand how to prepare the vehicle for the competition. It may include documentation how to connect to a SBC/SBM and upload files there, datasets, hardware specifications, communication protocols descriptions etc. If there is nothing to add to this location, the directory can be removed.

## Introduction

_This part includes the technical clarifications about the code: which modules the code consists of, how they are related to the electromechanical components of the vehicle, and what is the process to build the code to the vehicle’s controllers._

What This Code Does
This code controls a small self-driving car using a Raspberry Pi. It uses:

1 Motor (to move forward).

1 Servo (to steer left/right).

3 Ultrasonic Sensors (left, front, right) to detect obstacles.

How It Works
Setup

The motor and servo are connected to the Raspberry Pi’s GPIO pins.

The ultrasonic sensors send sound waves to measure distances.

Movement

The car moves forward at 40% speed (set by motor_speed=40).

The servo steers the wheels based on sensor readings.

Avoiding Obstacles

The code checks distances from the left and right sensors.

If one side is too close to an obstacle, the car steers away from it.

Example: If the right sensor detects something close, the car turns left.

Stopping

The car stops after 23.478 seconds (set by timer=23.478).

You can also stop it manually by pressing Ctrl+C.

Simple Breakdown of Key Parts
Motor Control → Moves the car forward.

Servo Control → Turns the wheels left or right.

Ultrasonic Sensors → Act like "eyes" to detect walls/obstacles.

Steering Logic → Adjusts steering if the car gets too close to one side.

What’s Missing?
The front sensor isn’t used (only left/right).

No reverse or speed changes (only forward at fixed speed).

Basic steering (could be smoother with better math).

