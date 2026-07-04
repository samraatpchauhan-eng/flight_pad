# Flight Pad (RP2040 Custom Macro Pad)

Flight Pad is a custom 3x3 mechanical macro pad featuring dual EC11 rotary encoders, built entirely on the high-performance **Raspberry Pi RP2040** microcontroller architecture and powered by **QMK Firmware**. 

It is designed to streamline flight simulator camera controls, and media navigation with zero-latency input processing.

## Features:
* **Custom Layout:** 3x3 Matrix Grid + 1 Integrated Encoder Switch (10 Keys Total).
* **Dual Encoders:** Dual EC11 Encoders for precise, media adjustments (like brightness, or volume).
* **Ergonomic Design:** Engineered for comfortable desktop use.
* **RP2040 Power:** Driven by the RP2040 chip for rapid response times and effortless flashing.

---

## CAD Model & Case Assembly
Everything fits together precisely using a layered enclosure design. The case includes structural mounting points for the PCB, plates, and components to ensure zero deck-flex during heavy use. Please note the keycaps used in these renders are generic .STEP models downloaded from the internet, and any standard MX keycap should work.

### Case Assembly & Fitment Exploded View
*An isometric 3D CAD visualization highlighting how the PCB, switches, encoders, and structural enclosure layers interface together seamlessly.*

<img width="1920" height="1440" alt="flight_pad_2026-Jun-16_03-59-39AM-000_CustomizedView15204062208" src="https://github.com/user-attachments/assets/a52d414a-1786-48f1-b706-a618cae95838" />

<img width="490" height="577" alt="Case_Assembly Fitment3" src="https://github.com/user-attachments/assets/32c04a14-b407-429f-bca6-210585d88565" />

<img width="552" height="651" alt="Case_Assembly Fitment2" src="https://github.com/user-attachments/assets/e7864b42-46c4-44ec-98c8-03551f7eb34e" />

<img width="858" height="817" alt="Case_Assembly Fitment1" src="https://github.com/user-attachments/assets/bb532b33-610c-4723-ba97-c04285c5f0f7" />



---

## PCB Design
The underlying electronics were engineered in KiCad. The board features clean routing paths optimized for the RP2040 pin configurations and a solid matrix layout to handle both the key switches and rotary encoders.

### Schematic Design
*The underlying circuit schematic mapping the switch matrix routing, diode placement, and dual encoder connections to the microcontroller.*

<img width="1569" height="824" alt="Electrical_Schematic_Diagram" src="https://github.com/user-attachments/assets/13821b64-ee1f-4d83-ac3a-8cf2f83e458d" />

### PCB Layout Architecture
*The routed printed circuit board design detailing trace paths, footprints, and physical alignment.*

<img width="1150" height="1194" alt="PCB_Layout" src="https://github.com/user-attachments/assets/b3d9472c-f2ce-40f6-be02-54c94e1141a8" />

---

## Firmware Overview & Default Keymap
This macro pad utilizes **QMK Firmware** for all input processing. The keys are configured in a standard matrix, while the encoders are tracked using hardware interrupts for maximum precision.

### Key Matrix (3x3 Grid)
| Row | Column 1 | Column 2 | Column 3 |
| :--- | :---: | :---: | :---: |
| **Row 0** | `Ctrl+6` | `Ctrl+1` | `Ctrl+7` |
| **Row 1** | `Ctrl+9` | `Ctrl+5` | `Ctrl+8` |
| **Row 2** | `L` | `C` | `R` |

### Rotary Encoder Functionality
* **Encoder 1 (Left/Volume):** * Clockwise: `Volume Up` | Counter-Clockwise: `Volume Down`
  * Integrated Push Switch: `MUTE`
* **Encoder 2 (Right/Brightness):** * Clockwise: `Screen Brightness Down` | Counter-Clockwise: `Screen Brightness Up`

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
* **1x** USB-C wire with data transfer

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
**Please Note that AI was utilized for some basic debugging of the Keyboard.JSON, and Keymap.C files in VS.Code**
