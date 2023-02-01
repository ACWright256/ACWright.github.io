---
layout: page
title: FPGA Design
permalink: /fpgadesign/
---


# FPGA Design
The FPGA is composed of an SPI module, a data storage module, and a display module. The SPI module receives data from the microcontroller and sends the data to the data storage module. If the SPI module completes the transaction and the display completes a frame, the data gets stored on flip-flops to be read by the display module.


The display module is composed of a main FSM, a color PWM FSM, a column shift FSM, color mapping combinational logic, and coordinate mapping combinational logic.

The SPI data on the flops first reaches the coordinate mapping combinational logic. This combinational logic assigns pixel values based on the integer value of the SPI data and the current selected rows. This row data is sent to the color mapping combinational logic, where colors are assigned in a gradient based on the selected row and row data. This data is then sent to the Color PWM module, where the output RGB values of each row pixel are assigned using PWM. This row data is then shifted out to the shift registers on the matrix display.

## FPGA Schematics and Block Diagrams
### Top Level Schematics
<div style="text-align: center">
  <img src="../assets/schematics/FPGA_overview.png" alt="fpgaoverview" width="600" />
</div>

### Display module
<div style="text-align: center">
  <img src="../assets/schematics/display_module.png" alt="displaymodule" width="800" />
</div>

## FPGA Finite State Machines
### Main FSM
<div style="text-align: center">
  <img src="../assets/schematics/main_fsm.png" alt="displaymodule" width="600" />
</div>

### ColorMod FSM
<div style="text-align: center">
  <img src="../assets/schematics/colormod_fsm.png" alt="displaymodule" width="600" />
</div>


### Colshift FSM
<div style="text-align: center">
  <img src="../assets/schematics/colshift_fsm.png" alt="displaymodule" width="400" />
</div>
