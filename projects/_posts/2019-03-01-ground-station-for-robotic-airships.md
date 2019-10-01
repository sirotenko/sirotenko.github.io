---
layout: post
title:  "Ground station for robotic airships"
date:   2019-10-01 01:41:36 +0500
image:  /public/images/projects/airships.jpg
---

Ground station for robotic airships was developed by Alex Shipika, Sergey Birukov and me. It includes Getac rugged notebook, joysticks for airship control, GPS antenna.

![](/public/images/pictures/ground-station-for-airships.png)
![](/public/images/pictures/ground-station-for-airships-2.jpg)

A special software was written to run on notebook supplying main functional of ground station. This software have the following features: 
- exchange data with airship onboard control system through Wi-Fi;
- uses GPS to determine ground station coordinates;
- visualizes telemetry and diagnostic data;
- gives interface to build, save and load flight tasks;
- receives compressed video data from airship on-board camera and shows it in video window;
- supports airship and onboard PTZ camera control through joysticks;
- allows to control airship in semiautomatic mode (double click on map to order airship to move to point).

## My contribution

I was responsible for overall software architecture development. Also I've developed video coding, transmission, decoding and viewing, joysticks support, some map navigation and flight task building features.