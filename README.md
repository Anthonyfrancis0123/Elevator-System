# Elevator-System
## CODESYS V3.5 PLC project for an Elevator Control System.

This project contains the device configuration, PLC logic (Structured text and Ladder), timers, variables, and a full HMI/visualization layout

## Device Information
- Codesys COntrol Win V3
- Vendor: 3S-Smart Software Solutions GmbH
- Version 3.5.19.70
- Windows based software

## PLC Logic (Main Program- PLC_PRG)
INPUTS (Buttons)
- MainStart - Main elevator switch
- C0, C1, C2, C3 - Floor call buttons
- EButton - Emergency button 

OUTPUTS
- Motor1 - Elevator motor control
- Motor2 - Elevator doors control
- GL, L1, L2, L3 - Level Indicators
- OpenDoor, CloseDoor - Door signals
- Ebuz - Emergency buzzer

TIMERS
- TON0 to TON4 - Motor1 running time
- TON5 - Doors openinng time
- TON6 - Open doors waiting time
- TON7 and TON8 - Doors closing time

PROGRAM BEHAVIOUR
The logic defines:
- The system has four floors: Ground floor (GL), Level 1 (L1), Level 2 (L2) and Level 3 (L3)
- It is made of one H-bridge-controlled DC motor that can move up or down (Motor1)
- An additional H-bridge-controlled DC motor for opening and closing of the elevator door (Motor2)
- The elevator has four commands buttons (C0, C1, C2 and C4) for each floor
- Command buttons are normally open buttons configured in LOW mode
- Only one button can be pressed at a time.
- When a floor button is pressed, the motor runs for 6 seconds to open the door and then closes.
- The elevator has four level sensors to detect whether the elevator has reached a specific floor, a HIGH-level logic output is triggered otherwise, the level remains LOW.
- Each motor run per floor takes 8 seconds whether it is an upward or downward motion.
- The motor runs forward or reverse depending on which floor is pressed and on which it is currently.

## Wiring diagram

<img width="1123" height="704" alt="image" src="https://github.com/user-attachments/assets/eec2decc-10d9-457f-91b9-51b3da6c413c" />

