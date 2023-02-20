---
layout: page
title: Circuit Design
permalink: /auv/circuitdesign/
exclude: true
---

[Back to project](/auv)

## Pressure Sensor
<div style="text-align: center">
  <img src="../../assets/schematics/auv/pressure_schem.png" alt="pressuresensor" width="1000" />
</div>
The pressure sensor circuit was designed to amplify the low voltage pressure sensor signal to cover the full bit range of the Teensy's onboard ADC peripheral. The amplifier had a gain of 25, which was determined by the feedback resistor R1 and parallel combination of R2 and R3. Resistors R2 and R3 composed a voltage divider, which created a virtual ground at 0.78 V. The purpose of this virtual ground was to prevent overdriving at atmospheric pressure. 

## Sonar
<div style="text-align: center">
  <img src="../../assets/schematics/auv/sonar_schem.PNG" alt="sonar" width="1000" />
</div>
The sonar system utilized a high-frequency pulse to detect reflections from both the seafloor and distant objects. The speaker produced a 13.8 kHz triangle wave pulse with a pulse width of 500 μs to achieve a high spatial resolution. For paths with a length difference less than 0.75 m, reflected pulses overlapped, causing multipath interference. The high signal frequency ensured that reflections were isolated from low-frequency noise.

The circuit generated a 500 μs triangle wave pulse at 13.8 kHz using a 555 timer triggered by the Teensy. The pulse triggered a voltage-controlled oscillator, which generated a triangle wave amplified by a speaker amplifier with a power of 5 W.  Key components were R8, C7, R11, C11, R17, R18, and C12, which determined the pulse width, frequency, gain, and frequency response of the amplifier. The potentiometer RV1 could be adjusted to change the triangle wave frequency, compensating for component tolerances.

The microphone signal was amplified using a three-stage non-inverting amplifier with an overall gain of 512. Op amps were used to center the signal, and a 1.65 V bias was generated using the remaining op amp and voltage regulator. A high pass Sallen-Key filter was introduced to remove low frequencies, and the output was sampled by the Teensy at 100 kHz, which was sufficient to record the 13.8 kHz signal.

