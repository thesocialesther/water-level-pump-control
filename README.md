# Automated water tank level monitoring and pump control

**Author: Oluwaferanmi Esther Onifade**

A PIC16F877A-based water tank controller designed and simulated in Proteus. It measures a represented tank level, displays the percentage on a 16×2 LCD, and switches a pump through a relay to maintain water between low and high thresholds.

## How the controller works

An analog potentiometer represents the level sensor, supplying a 0–5 V signal to the PIC's 10-bit ADC. The 0–1023 reading is converted to a 0–100% level for display and control.

The pump uses hysteresis:

- At **20% or below**, switch the pump on.
- At **90% or above**, switch the pump off.
- Between those thresholds, retain the previous pump state.

This avoids repeatedly switching the pump around a single threshold. Red and green LEDs indicate the controller state.

## Hardware and simulation

The reported design uses a PIC16F877A at 20 MHz, an LM016L LCD, a BC547 relay-driving transistor, a 5 V relay, and a simulated DC motor as the pump.

| Connection | Role |
| --- | --- |
| AN0 / RA0 | Analog level input |
| RC0 | Relay/pump control |
| RB0 | Red status LED |
| RB1 | Green status LED |

Confirm the complete LCD and driver wiring against the included schematic before rebuilding firmware.

## Repository contents

- `WATER_CONTROL_LEVEL_PUMP.pdsprj`: original Proteus simulation project.
- `firmware-excerpts.txt`: three code excerpts recovered from the project report.

The excerpts describe parts of the control logic but are not a complete compilable MikroC program.

## Open and reproduce

1. Open the project in Proteus 8 Professional.
2. Check the PIC clock setting and schematic connections.
3. Assign the matching compiled `.hex` file to the PIC's Program File property once it is available.
4. Start the simulation and vary the level potentiometer.
5. Check percentage display, low-level pump activation, high-level shutoff, and state retention between thresholds.

The original complete firmware and compiled HEX are not yet included, so a fresh clone does not currently contain everything required to run the simulation.

## Documented results and remaining files

The project report records pump activation at 17% and shutoff at 90%. These are reported observations, not a new simulation test performed for this upload.

The remaining release materials are the full MikroC `.c` source, project file (such as `.mcppi`), matching `.hex`, and the final report or simulation screenshots. A bill of materials and full wiring description would also help others reproduce the design.
