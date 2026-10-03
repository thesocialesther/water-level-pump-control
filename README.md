# Automated water tank level monitoring and pump control
Author: Oluwaferanmi Esther Onifade

PIC16F877A water-level controller simulated in Proteus. An analog input represents tank level, a 16x2 LCD displays the percentage, and a relay controls the pump. The documented hysteresis turns the pump on at 20% or below and off at 90% or above.

## Files
- WATER_CONTROL_LEVEL_PUMP.pdsprj: original Proteus project.
- firmware-excerpts.txt: three code excerpts recovered from the project report; these are not complete compilable firmware.

## Open the simulation
Open the project in Proteus 8 Professional. The report describes a 20 MHz clock, AN0 sensing, relay output on RC0, and status LEDs on RB0/RB1. Confirm the actual schematic wiring before attaching firmware.

The original complete MikroC source and compiled HEX have not yet been located. The simulation may need its PIC Program File path updated to a matching HEX file before it can run. This export preserves the original simulation and report excerpts; it does not invent missing firmware or claim a new simulation test.
