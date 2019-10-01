---
layout: post
title:  Miniairship based mobile robot "Sterkh"
date:   2019-10-01 01:41:36 +0500
image:  /public/images/projects/sterkh.jpg
---

## Project history

The main aim of this project is creation of an autonomous mobile robot based on airship. This project was started from the idea of Vyacheslav Pshikhopov in early 2000. After that a number of theoretical studies of this task was done. In 2005 our team finally found money to start an implementation of the project. The main part of the robot, which was called "Sterkh" (white crane) - the carrier is a remotely controlled mini-airship "RD-2.5" from Rosaerosystems company. It is only 7.44 meters long and has a volume of 24 m3. 

First Sterkh team was: Vyacheslav Pshikhopov (proj. leader), Ivan Korneev, Victor Cabanets, Sergey Pisarenko, Mikhail Sirotenko. In the 2005 International Robotics Exhibition at Moscow we've  presented fist version of Sterkh and were awarded by All-Russian Exhibition Center Medals. Since 2006 I become a technical leader of this project. Current Sterkh team is: Vyacheslav Pshikhopov (sci. leader, control algorithms), Mikhail Sirotenko (tech. leader, software), Mikhail Medvedev (algorithms),  Roman Fedorenko (software),  Boris Gurenko (hardware).

## Robot descriprion

Robot consists of soft envelope filled with helium and gondola, equiped by two propellers with variable traction direction, PTZ camera, control and comunication hardware. 

![](/public/images/pictures/miniairship-based-mobile-robot-sterkh.png)

Onboard hardware consists of following modules:
- CPU module CMX58886CX (RTD Embedded Technologies) running QNX 6.1 and control software;
- frame grabber module Model 512 (Sensoray) used to grab video from ;
- HESC104 power supply module (Tri-M Engineering);
- Wi-Fi communication module (D-Link);
- Kompanav integrated navigation module (Teknol) with GPS antena (Garmin);
- ATMega128 based microcontroller board for low-level actuators control and feedback;
- 2 servos for tracrion direction control;
- 2 encoders on propellers engines;
- SD53CBW-F-E1-X PTZ camera (Pelco);
- 2 batteries.

CPU board is running QXN 6.1 RTOS with our control software RLCOnboard. RLCOnBoard integrates data from navigation system, analises fligt task and generates controls. Controls are sent to MCU board, which generates low-level control signals to actuators and receives feedback from encoders. Also RLCOnBoard receives video data, encode it to MPEG at realtime using Sensoray board and transmits to Ground station with other telemetry data through Wi-Fi router.  

## My contribution

At recent three years I was a technical leader of this project and was responsible for overall archeticture development, including equipement choise and general work algorithms development. I have developed RLCOnBoard control software architecture, planning module, network data exchange module, compuer vision module. I also participated in development of Ground station. 

## Video

This video shows mini-airship based robot Sterkh flying and transmiting video from onboard PTZ camera. Video was taken at Robotics exhibition in All-Russian Exhibition Center, Moscow, 2005.

<iframe width="560" height="315" src="https://www.youtube.com/embed/i0PjJDAwG3M" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Next video shows Sterkh fighting with the wind.

<iframe width="560" height="315" src="https://www.youtube.com/embed/D-3p8o3hNWw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>