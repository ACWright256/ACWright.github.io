---
layout: page
title: Documentation
permalink: /doc/
---


# Source Code Overview
<!-- This section should include information to describe the organization of the code base and highlight how the code connects. -->

The source code for the project is located in the Github repository [here](https://github.com/ACWright256/MicroPsFinalProject).

# New Hardware
The new piece of hardware for this project is the Adafruit LED matrix. This hardware is controllable by shifting RGB channel data through two row pins and into the LED matrix shift registers. A LATCH signal must be asserted afterwards to push the bits from the shift register to the matrix row. An OE (output enable) is then asserted to wipe the screen and control brightness. The timing diagram for this transaction is below.
<div style="text-align: center">
  <img src="../assets/schematics/led_matrix_timing.png" alt="ledmatrix" width="800" />
</div>
The new Microcontroller peripheral is the ADC, which converts the analog signal to a digital signal. 

# Bill of Materials
<!-- The bill of materials should include all the parts used in your project along with the prices and links.  -->

| Item | Part Number | Quantity | Unit Price | Link |
| ---- | ----------- | ----- | ---- | ---- |
| Adafruit 64x64 RGB LED Matrix - 2.5mm Pitch - 1/32 |  3649 | 1 | $54.95 |  [link](https://www.adafruit.com/product/3649) |
| STM32L432KC MCU |  N/A | 1 | N/A |  N/A |
| UPduino v3.1 FPGA |  N/A | 1 | N/A |  N/A |
| TL084 FET-Input Operational Amplifiers |  TL084 | 1 | N/A |  [link](https://www.ti.com/lit/ds/symlink/tl082.pdf?ts=1670252579810&ref_url=https%253A%252F%252Fwww.google.com%252F) |
| MCP601 Operational Amplifier |  MCP601 | 1 | N/A |  [link](https://ww1.microchip.com/downloads/en/DeviceDoc/21314g.pdf) |
| 4 Position DIP Switch |  N/A | 2 | N/A |  N/A |
| 10K Potentiometer |  N/A | 3 | N/A |  N/A |
| 10K Potentiometer |  N/A | 3 | N/A |  N/A |
| Resistors |  N/A | 14 | N/A |  N/A |
| Capacitors | N/A  | 4 | N/A |  N/A |
| Sheet Wood |  N/A | 2 | N/A |  N/A |

**Total cost: $54.95**
