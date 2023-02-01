---
layout: page
title: Results
permalink: /results/
---

# Results
The LED matrix displays analog signals as expected. The knobs and switches on the signal displayer successfully allow the user to control the offset, amplification, and attenuation of the signal.The LED matrix is able to display sine waves for varying input frequencies. 

Unforunately, the scope suffers from aliasing. This is not a problem with the FPGA, ADC, or MCU, but is rather a flaw with the front end analog circuitry. Because the time division functionality is a last-minute addition, the low-pass filter was not designed with the ability to switch corner frequencies. 

The LED matrix's lack of a datasheet or timing diagrams makes hardware development tricky. However, there are a pleathora of online resources, which aided the process.

The early design decision made for the FPGA code also proved to be a challenge. The emphasis on modularity resulted in a bloated design that could have been achieved with fewer state machines and fewer connecting wires. 

The analog wave display can display a 100 kHz signal. No triggering functionality was implemented, but even for high frequency signals, the sinusoid is discernable. 



[Demo](https://www.youtube.com/watch?v=X-L50WvtRKw)

