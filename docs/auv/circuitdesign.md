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

The pressure sensor amplifier was designed to allow the Teensy to record high resolution pressure data over a small range of depths. The non-inverting amplifier (above) used the voltage divider with R2 and R3 to create a virtual ground at 0.78V, which prevented the amplifier from overdriving when the sensor was at atmospheric pressure. The amplifier had a gain of 25, due to the feedback resistor R1 and the parallel combination of R2 and R3. A pressure sensor voltage of 0.88 V yielded an amplifier output of 3.3 V, corresponding to a pressure of 106 kPa and a maximum depth of approximately 0.6 m. The observed maximum depth during testing was closer to 1.5 m, likely due to variations in the value of R3 and the pressure sensor’s output characteristics. The high sensitivity of this circuit was useful for observing how changes in robot depth affected the timing of sonar reflections. During deployment the robot only descended to 0.7 m because the sonar system would not detect reflections if the speaker was too close to the seafloor, so the limited range of the pressure sensor amplifier was not an issue for these experiments.


## Sonar
<div style="text-align: center">
  <img src="../../assets/schematics/auv/sonar_schem.PNG" alt="sonar" width="1000" />
</div>


The designed sonar system drove a high frequency pulse into a transducer and recorded reflections using a microphone. The speaker power and microphone gain were optimized to ensure that reflections were detected from the muddy seafloor and distant objects. To give the system a high spatial resolution, the speaker produced a 13.8 kHz triangle wave pulse with a pulse width of 500 μs. The pulse width determines the minimum spatial separation of the sonar targets. The output wave travels 0.75 m through the water in 500 μs, so reflected pulses would overlap and cause multipath interference if two paths had a difference in length less than 0.75 m. The high signal frequency ensured that reflections were detected and isolated from low-frequency noise within the 500 μs pulse. The pulse frequency also determines the target size resolution of the sonar system, as objects show little reflection if they are significantly smaller than the signal wavelength. A 13.8 kHz signal has a wavelength of 10.9 cm, but the Teensy’s sampling rate and the signal pulse width prevented such precise measurements.

The circuit (above) was designed to generate a 500 μs triangle wave pulse at a frequency of 13.8 kHz. The Teensy triggered a 555 timer, which outputs a 500 μs pulse. This pulse pulled down the MOD pin of a 566 voltage controlled oscillator, which generated a triangle wave that went into the speaker amplifier. The triangle wave was amplified and driven through the audio exciter at a power of 5 W. Key component values in this system were R8 and C7, which determined the pulse width; R11 and C11, which determined the triangle wave frequency; and R17, R18, and C12, which determined the gain and frequency response of the amplifier. The potentiometer RV1 could be adjusted to change the triangle wave frequency from 0 Hz to 13.8 kHz. Although this application only required a fixed frequency, RV1 allowed the user to precisely set the output frequency and compensate for component tolerances.
	
The microphone signal was AC coupled to a three stage non-inverting amplifier with an overall gain of 512. Spreading the gain across three op amps improved the bandwidth and high-frequency amplifier gain. Each op amp had a virtual ground at 1.65 V to center the signal, since the Teensy ADC could only record voltages from 0 to 3.3 V. This 1.65 V bias was generated using the remaining op amp of the MCP6004 as a buffer, and the 5 V power came from a L7805 voltage regulator. Testing at pHake Lake revealed that when the microphone was underwater, water currents created strong low frequency signals that overpowered the audio and caused the amplifier to rail out. The high pass Sallen-Key filter at U1D was introduced to remove these low frequencies and isolate the reflected sonar signal. The Teensy sampled the amplifier output at 100 kHz, which according to the Nyquist sampling theorem was sufficient to record the 13.8 kHz signal without aliasing.
