---
layout: page
title: Autonomous Underwater Vehicle
permalink: /auv/
---

<div style="text-align: center">
  <img src="../assets/img/auv/robot.PNG" alt="robot" width="800" />
</div>
<n></n>


### Overview
<n></n>
The goal of this project was to create an autonomous underwater vehicle to collect sonar data, GPS data, and depth data for our experimental engineering course. 

The robot navigated to multiple waypoints using an open loop control system, collected sonar data using a Sallen-Key filter connected to an ADC on a Teensy, and collected pressure data using a simple amplifier circuit.

We verified the efficacy of our sonar system by comparing the measured depth to actual depth across different locations in Dana Point.

For more information, click [here](https://drive.google.com/file/d/16dLYdiTFBxq6Ycjpd2Q3qWm6e8IngI3I/view?usp=sharing)

## Sonar
<div style="text-align: center">
  <img src="../../assets/schematics/auv/sonar_schem.PNG" alt="sonar" width="1000" />
</div>