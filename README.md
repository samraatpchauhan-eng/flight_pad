# Flight Pad (RP2040 Custom Macro Pad)

Flight Pad is a custom 3x3 mechanical macro pad featuring dual EC11 rotary encoders, built entirely on the high-performance **Raspberry Pi RP2040** microcontroller architecture and powered by **QMK Firmware**. 

It is designed to streamline flight simulator camera controls, and media navigation with zero-latency input processing.

## Features:
* **Custom Layout:** 3x3 Matrix Grid + 1 Integrated Encoder Switch (10 Keys Total).
* **Dual Encoders:** Dual EC11 Encoders for precise, incremental simulator adjustments (like altitude, heading, or volume).
* **Ergonomic Design:** Engineered with an integrated mechanical case tilt for comfortable desktop use.
* **RP2040 Power:** Driven by the RP2040 chip for rapid response times and effortless flashing.

---

## CAD Model & Case Assembly
Everything fits together precisely using a layered enclosure design. The case includes structural mounting points for the PCB, plates, and components to ensure zero deck-flex during heavy use. Please note the keycaps used in these renders are generic .STEP models downloaded from the internet, and any standard MX keycap should work.

### Case Assembly & Fitment Exploded View
*An isometric 3D CAD visualization highlighting how the PCB, switches, encoders, and structural enclosure layers interface together seamlessly.*
<img src="flight_pad/flight_pad_2026-Jun-16_03-59-39AM-000_CustomizedView15204062208.jpg" alt="Case Assembly and Fitment" width="500"/>

<img src="flight_pad/Case_Assembly&Fitment1.jpg" alt="Case Assembly and Fitment" width="500"/>

<img src="flight_pad/Case_Assembly&Fitment2.jpg" alt="Case Assembly and Fitment" width="500"/>

<img src="flight_pad/Case_Assembly&Fitment3.jpg" alt="Case Assembly and Fitment" width="500"/>

*Designed completely from scratch in Autodesk Fusion 360.*

---

## PCB Design
The underlying electronics were engineered in KiCad. The board features clean routing paths optimized for the RP2040 pin configurations and a solid matrix layout to handle both the key switches and rotary encoders.

### Schematic Design
*The underlying circuit schematic mapping the switch matrix routing, diode placement, and dual encoder connections to the microcontroller.*
<img src="flight_pad/Electrical_Schematic_Diagram.png" alt="Case Assembly and Fitment" width="500"/>

### PCB Layout Architecture
*The routed printed circuit board design detailing trace paths, footprints, and physical alignment.*

<img src="flight_pad/PCB_Layout.png" alt="Case Assembly and Fitment" width="500"/>

---

## Firmware Overview & Default Keymap
This macro pad utilizes **QMK Firmware** for all input processing. The keys are configured in a standard matrix, while the encoders are tracked using hardware interrupts for maximum precision.

### Key Matrix (3x3 Grid)
| Row | Column 1 | Column 2 | Column 3 |
| :--- | :---: | :---: | :---: |
| **Row 0** | `6` | `1` | `7` |
| **Row 1** | `9` | `5` | `8` |
| **Row 2** | `L` | `C` | `R` |

### Rotary Encoder Functionality
* **Encoder 1 (Left/Volume):** * Clockwise: `Volume Up` | Counter-Clockwise: `Volume Down`
  * Integrated Push Switch: `MUTE`
* **Encoder 2 (Right/Navigation):** * Clockwise: `Screen Brightness Down` | Counter-Clockwise: `Screen Brightness Up`

---

## Bill of Materials (BOM)
Here is the complete component breakdown required to build the Flight Pad:

* **9x** Cherry MX Mechanical Switches
* **9x** MX-Compatible Keycaps
* **9x** 1N4148 DO-35 Switching Diodes *(Crucial for matrix isolation and anti-ghosting)*
* **2x** EC11 Rotary Encoders with integrated push-switches
* **1x** Raspberry Pi RP2040 Microcontroller Board
* **1x** Custom Case Enclosure (3D printed/CNC components)
* **4x** M3x16mm screws

---

## How to Flash
1. Disconnect the USB cable from the Flight Pad.
2. Press and hold the physical **BOOT** button on the RP2040 controller board.
3. Reconnect the USB cable while holding the button, then release it.
4. A virtual drive named **RPI-RP2** will mount to your operating system.
5. Drag and drop the `flight_pad_default.uf2` binary file directly onto the root of the drive.
6. The device will automatically flash, reboot, and initialize as an operational HID keyboard device.

---

## AI Attribution Note
**Please Note that AI was utilized to format this .README file, aswell as some basic debugging of the Keyboard.JSON, and Keymap.C files in VS.Code**
