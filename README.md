# PCB-board-
PCB board 

# 555 Timer LED Flasher Circuit (Night Sky Beacon)

An introductory hardware project designing an astable multivibrator circuit using the classic NE555 Timer IC. This project serves as a foundational step toward understanding analog circuit behavior, schematic capture, and PCB routing parameters based on IPC standards.

IPC 
 Project Overview
This circuit generates a continuous square wave pulse that flashes an LED at a specific frequency. It acts as an electronic "beacon," reminiscent of a pulsing star in the night sky. The objective is to transition from a theoretical breadboard layout to a physical, manufactured PCB using EDA tools (KiCad/Altium).

##  Scientific Formulation & Calculations
The frequency ($f$) and duty cycle ($D$) of the pulsing LED are governed by the charge and discharge times of the capacitor ($C_1$) through resistors ($R_1$) and ($R_2$).

- **Charge Time (High Output):** 
  $$T_h = 0.693 \times (R_1 + R_2) \times C_1$$
- **Discharge Time (Low Output):** 
  $$T_l = 0.693 \times R_2 \times C_1$$
- **Total Period ($T$):** 
  $$T = T_h + T_l = 0.693 \times (R_1 + 2R_2) \times C_1$$
- **Frequency ($f$):** 
  $$f = \frac{1}{T} = \frac{1.44}{(R_1 + 2R_2) \times C_1}$$

### Component Selection for ~1.5 Hz Frequency:
- $R_1 = 1K\Omega$
- $R_2 = 47K\Omega$
- $C_1 = 10\mu F$
- **Resulting Frequency:** ~1.49 Hz (The LED will flash approximately 1.5 times per second).

## 🗺️ Schematic Pin Mapping
The NE555 IC is configured in **Astable Mode**:
1. **GND (Pin 1):** Connected to Power Supply Ground.
2. **Trigger (Pin 2):** Tied to Threshold (Pin 6) and $C_1$ positive terminal.
3. **Output (Pin 3):** Drives the LED via a $330\Omega$ current-limiting resistor.
4. **Reset (Pin 4):** Tied to $V_{CC}$ to prevent accidental reset.
5. **Control Voltage (Pin 5):** Connected to ground via a $10nF$ ceramic capacitor to filter noise.
6. **Threshold (Pin 6):** Connected to Pin 2 and the junction of $R_2$ and $C_1$.
7. **Discharge (Pin 7):** Connected to the junction of $R_1$ and $R_2$.
8. **$V_{CC}$ (Pin 8):** Connected to +5V to +9V Power Supply.

##  PCB Design Parameters & Best Practices
- **Trace Width:** Minimum 0.25mm (10 mils) for signal traces; 0.5mm (20 mils) for $V_{CC}$ and GND copper tracks to minimize parasitic resistance.
- **Form Factor:** Compact 2-layer FR4 board layout.
- **Decoupling:** Place the 10nF noise-filtering capacitor as close as physically possible to Pin 5.

## 📁
Repository Structure
- `/Schematics` : Contains KiCad/Altium schematic files (`.sch`).
- `/Layout` : Contains PCB routing files (`.pcb`).
- `/Manufacturing_Files` : Industry-standard **Gerber Files (X2)** and Bill of Materials (BOM) ready for fabrication.

# [: Arduino Nano Custom Baseboard]

## Overview
This is an industry-standard PCB project designed strictly following IPC guidelines. ]

## Key Features & IPC Standards Followed
* **Design Standard:** Designed according to **IPC-2221** (Generic Standard on Printed Board Design).
* **Footprints:** Custom and library footprints validated against **IPC-7351B** for perfect land patterns.
* **Manufacturing Level:** Optimized for **IPC-A-610 Class 2** (Dedicated Service Electronic Products).
* **Trace Parameters:** Trace width calculated using IPC-2221 calculator for 1A current carrying capacity.

## Board Specifications
* **Layers:** 2-Layer / 4-Layer
* **Material:** FR-4 (IPC-4101 compliant)
* **Minimum Trace Width:** 12 mil
* **Minimum Clearance:** 10 mil
* **Via Size:** 0.3mm (Hole) / 0.6mm (Ring)

## Repository Structure
* `/Schematic` - PDF and Source Schematic files.
* `/Layout` - PCB design source files.
* `/Manufacturing` - Gerber files, Bill of Materials (BOM), and Pick & Place files.
* 


