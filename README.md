# usb-c-sd-card-reader-pcb
Custom USB-C microSD card reader hardware project featuring schematic design, PCB design and system validation.

# USB-C microSD Card Reader

A custom USB-C microSD card reader PCB designed around the **Genesys Logic GL823K** controller. This project covers the full hardware development flow, from component selection and 
schematic capture to PCB layout, PCB fabrication and assembly ordering, hardware bring-up, hardware debugging and successful memory card read validation.

## Overview

The goal of this project was to design and build a compact USB-C memory card reader that interfaces with a microSD card and communicates with a host device over USB.

This project was completed as a practical electronics and PCB design exercise, with a strong focus on:
- component selection
- schematic design
- PCB layout
- design for manufacture and assembly
- PCB fabrication and assembly ordering
- hardware bring-up
- power rail verification
- debugging and validation

## Key Design Approach

Before starting the design, I selected components carefully to make assembly easier and faster through **JLCPCB**. 
I made sure the parts I chose were available in **JLCPCB Basic** or **Extended** libraries so that the board could be manufactured and assembled with minimal friction.

This was an important practical lesson in designing not just for functionality, but also for **manufacturability** and **assembly convenience**.

## Main Components

The design used the following key parts:

- **GL823K-HCY04** — USB 2.0 flash card reader controller
- **TYPE-C 16PIN 2MD(073)** — USB-C connector
- **Molex 503398-1892** — microSD card connector
- **PRTR5V0U2X / PRTR5V0U2X,215** — USB ESD protection device
- supporting capacitors, resistors and power components for decoupling, pull-downs and signal support

## 3D image
<img width="642" height="282" alt="Screenshot 2026-04-11 at 00 45 47" src="https://github.com/user-attachments/assets/20bbc94b-93a6-4713-93d1-3e85b998f90c" />

## Printed board
![IMG_5067](https://github.com/user-attachments/assets/89e71145-4d97-4a54-9e89-9fdfbe232666)

## Features

- USB-C interface
- microSD card support
- GL823K-based controller
- Custom PCB design
- ESD protection
- Manufactured and assembled through JLCPCB
- Working prototype validated through hardware testing

## Tools Used

- **Altium Designer** for schematic capture and PCB layout
- **JLCPCB** for PCB fabrication and PCB assembly
- lab test equipment for bring-up and debugging
- USB host (Laptop) for functional testing

## Manufacturing and Assembly

As part of this project, I learned how to take a PCB from design stage to production by preparing and ordering both:
- **PCB fabrication**
- **PCB assembly (PCBA)**

This included selecting assembly-friendly parts, preparing manufacturing outputs, and understanding how to structure a design so it can move efficiently into production.

A key lesson was the value of checking component availability early in the design process rather than waiting until the board is finished.

## Bring-Up and Debugging

During initial testing:
-5v from usb works 
-3.3v from port 9 works 
-3.3v from port 13, 8 doesnt works

This prevented the board from functioning correctly at first. 

A structured debug process was used:
1. Verify USB input power
2. Check GL823K supply-related pins
3. Confirm which rails were active and which were missing
4. Isolate the failing rail
5. Inject external 3.3 V into the affected rail as a debug step

This confirmed the root cause. Once external 3.3 V was injected into the problematic rail, the board was able to function correctly and the memory card could be read successfully.

## Challenges Faced

One practical issue I encountered was with the **orientation of the microSD card connector**. I misplaced the insertion direction, which made inserting the card difficult and inconvenient during testing.

Although the board was made to work, this was an important design lesson:
- connector orientation matters just as much as electrical correctness
- usability should be considered during PCB design, not only circuit functionality
- physical interaction with the product is part of good hardware design

This is something I would improve in the next revision.

## Final Result

The project achieved a **working hardware prototype**.

### Outcome
- Board was successfully fabricated and assembled
- USB power-up was verified
- Hardware debugging identified the failing rail
- Memory card reader functionality was demonstrated
- The memory card was successfully read

## What I Learned

Through this project, I gained hands-on experience in:
- selecting components for both function and manufacturability
- designing a custom USB peripheral PCB
- preparing a board for **JLCPCB fabrication and assembly**
- choosing parts available in **JLCPCB Basic and Extended** libraries
- debugging mixed power and interface issues
- verifying PCB functionality through electrical measurements
- identifying board-level faults through structured troubleshooting
- appreciating the importance of connector placement and insertion orientation in real hardware products

## Future Improvements

For the next revision, I would focus on:
- improving the implementation of the affected supply rail
- reviewing critical pin connectivity and local decoupling
- improving connector orientation and mechanical usability
- adding clearer bring-up test points
- documenting test results with photos and measurements

## Project Status

**Prototype completed and functional.**

