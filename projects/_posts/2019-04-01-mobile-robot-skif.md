---
layout: post
title:  Mobile robot "Skif"
date:   2019-10-01 01:41:36 +0500
image:  /public/images/projects/skif.jpg
---

## Project history

The main aim of the project is development of autonomous wheeled mobile robot. It was started in early 2001 by students team (Korneev Ivan, Kabanets Vicror, Pisarenko Sergey, Shemaev Pavel, Kaveshnikov Nikolay, Shanin Dmitry) lead by Vyacheslav Khasanovich Pshikhopov. The purpose of the robot was a participation at the [International competition "Mobile robots"](http://www.google.com/url?q=http%3A%2F%2Fwww.mobilerobots.msu.ru%2F&sa=D&sntz=1&usg=AFQjCNFg0XB1XYzAwya0EsPr4xh0FU3zqA). The rules of competition supposed a students teams making their own robots for performing different tasks fully autonomously. The tasks was mainly connected with beacons (infrared lights distributed on the work field) and stripe. First version of robot, called "Skif" was finished in 2002 and was roughly experimental. Participation at competition in 2002 revealed some limitaions in the first version and it was decided to make a new one - "Skif-2". 

![](/public/images/pictures/skif1.jpg)
![](/public/images/pictures/skif2.jpg)

It a 2003 I've become a member of students laboratory "Robotics and Intelligent Systems" and joined the Skif team. In a 2005 I become a team captain. At that time the team consisted of me, Sergey Pisarenko, Roman Shamin, Victor Cabanets and Korneev Ivan. In the May of 2005 we took part in Mobile robotics competition, which was held at Technological Institute of Versallies University at Matnes-la-Jolie (France). Our robot took a first place at the "Mapping" contest. After that a new team of students was created to build the next generation of robot - "Skif-3". This version is the final for now.

![](/public/images/pictures/skif4.jpg)
![](/public/images/pictures/skif5.jpg)

## Robot description 

Robot have tank-like kinematic scheme, i.e. two driving wheels and one auxilary wheel.  

For now the robot consists of the following main parts:
- Pentium M based onboard computer;
- Microcontroller unit for low lever control;
- Two ethernet cameras for stereovision;
- One frontal camera for obstacle avoidance and lane traking;
- Two drives with encoders;
- Step-drive based beacon finder;
- Wi-fi router;
- Optionally Sick laser rangefinder.

Here's the structure (figure by Fedorenko Roman):

![](/public/images/pictures/skif-scheme.png)

The onboard computer is powered by QNX 6.2 realtime operating system. We use or own software for robot. It consists of two parts: onboard robot control software and base station interface and simulation software. Onboard soft is written in a scalable object oriented maner. It is a thread-based, i.e. uses a single thread for a certain subsystem.

Skif won the first place prize at "Mapping" competition (France, 2005)

![](/public/images/pictures/skif-winner.jpg)

## My contribution

In a different time I've been involved in different aspects of Skif development, including MCU-board design, software development and project leading. Particularly I've worked on the design and low-level software development of beacon finder device. The purpose of that device was to detect beacons beaming ifrared singnals at 16 KHz frequency, determine the direction to that beacons and transmit data to MCU using I2C protocol. This work have included also modifications of MCU software and development of special Windows software for debug purposes.

Another significant part which I've worked on is control software for QNX-powered onboard computer "SkifOnBoard". I have developed the architecture of SkifOnBoard, Planner module, worked on Computer vision, Network modules.

## Videos

This video demonstrates Skif-3 robot, moving along circle while Victor tries to push it out of the trajectory. Control algorithms for such trajectory motion are designed by my sci. adv. Pshikhopov V.Kh.

The latest Skif team.

<iframe width="560" height="315" src="https://www.youtube.com/embed/QkF_iFIBH2E" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Second video shows the plot of motion, shown on previous video.

<iframe width="560" height="315" src="https://www.youtube.com/embed/i9GvgE5j2sc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>