---
layout: page
title: Project Overview
permalink: /
exclude: true
---

<div style="text-align: left">
  <img src="./assets/img/hmc_logo.png" alt="logo" width="100" />
  <img src="./assets/img/Logo.png" alt="logo" width="100" />
</div>

<n></n>
<div style="text-align: center">
  <img src="./assets/img/scope.jpg" alt="logo" width="800" />
</div>
<n></n>

[Demo](https://www.youtube.com/watch?v=X-L50WvtRKw)

# Abstract
Oscilloscopes and analog signal measurement tools are an essential part of electronics. At first glance, they simply record the magnitude of electronic signals, but hidden beneath is the ability to calculate important signal characteristics such as frequency content. These features were goals that the team set out to implement on a self fabricated oscilloscope created during the Fall 2022 semester. The oscilloscope is made to take in input sinusoidal signals with a peak to peak voltage between one and five and a frequency range up to 100 kHz. The overall design can be broken up into three major components that are outlined on this website. First, analog circuits are used to perform preprocessing on the raw input signal, such as filtering, and to handle interactive functionalities including signal scaling and offsetting. This signal then enters the STM32 ADC where it is digitized and sent over SPI protocol to the FPGA. From there the FPGA displays the digitized data onto a 64 by 64 LED matrix. Each of these processes and the steps taken to accomplish these operations are outlined in individual sections on this website. The goal of this project was to become more technically versed with digital hardware, but the team came out of the project learning far more!
<n></n>

# Project Motivation
The team was motivated to uncover the complexities of an oscilloscope. Oscilloscopes are a tool that we both use extensively and as a fundamental piece of electronic technology, we realized that we have taken it for granted. In this project we wanted to honor oscilloscopes by gaining a deep understanding of the electronics behind the technology and translate that knowledge into a tangible product. On this website you can follow our one month learning journey!
<n></n>

# System Block Diagram

<div style="text-align: center">
  <img src="./assets/schematics/system_block_diagram.png" alt="system" width="800" />
</div>
