---
layout: page
title: Analog Circuit Design
permalink: /analogdesign/
---
<div style="text-align: center">
  <img src="../assets/schematics/analog.png" alt="analogdesign" width="800" />
</div>

The goals of the front end analog circuitry are to provide an antialiasing filter, signal amplification, signal attenuation, signal offset, and time scaling. The analog front end contains a main circuit, and a probe. The probe is a hand-made shielded cable that elminates magnetic disturbances on the input signal wire.

The analog circuit contains 5 main stages: the Sallen-Key low-pass filter, the amplifier, the attenuator, the offsetter, and the unity gain buffer.

## Sallen-Key filter
The Sallen-Key filter is configured with a corner frequency of 100 kHz. Ideally, this stage should prevent signal aliasing. 
However, the last-minute inclusion of discrete time divisions means that the filter is insufficient for lower sampling rates. Because the corner frequency is fixed, noise below 100khz but above the sampling rate can still cause aliasing.

## Amplifier
The amplifier stage is modeled after a guitar amplifier circuit that contains a potentiometer for gain factor adjustments. This amplifier circuit is configured in a non-inverting topology, which eliminates possible complex phase shift issues.

## Attenuator
The attenuator stage is a variable voltage divider connected to an op amp in unity gain negative feedback. The purpose of the op amp is to prevent loading between circuit stages.

## Offsetter
The offsetter stage contains a variable voltage divider. The output from this divider is added to the input signal to create the offset. The large capacitor near the input of the circuit prevents the output of this stage from attenuating near 1-10 Hz.

## Unity Gain Buffer
The purpose of the unity gain buffer is to limit the voltage range of the signal so that it complies with the requirements set by the ADC. The ADC can take input voltages from 0 V to 3.3 V reliably, and has a maximum rating of -0.3 V to 4 V. 

Because the op amp is configured in a unity gain negative feedback loop, the manufacturer characterstics can have a large impact on signal quality.

Op amp rail hysteresis was a problem the team encountered when adding the unity gain buffer to the rest of the circuit. Rail hysteresis caused the signal to "jump" to the rail, even if the signal value was below the rail. Eventually, this distortion was lessened when the analog circuit was moved from the breadboard to the perfboard. 

## The Probe
Initially, the probe was designed in accordance to traditional oscilloscope probe schematics. However, under testing, the probe behaved like a low pass filter, and attenuated desired signals. Due to time limitations, the decision was made to elminitate the probe circuitry, and convert the probe into a shielded cable. 

## Final Circuitry
<div style="text-align: center">
  <img src="../assets/schematics/final_circuit.jpg" alt="analogdesign" width="500" />
</div>

## Prototype Circuitry
<div style="text-align: center">
  <img src="../assets/schematics/prototype_circuit.jpg" alt="analogdesign" width="500" />
</div>

