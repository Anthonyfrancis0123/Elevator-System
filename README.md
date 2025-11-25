# Elevator-System
## CODESYS V3.5 PLC project for an Elevator Control System.

This project contains the device configuration, PLC logic (Structured text and Ladder), timers, variables, and a full HMI/visualization layout

## Device Information
- Codesys COntrol Win V3
- Vendor: 3S-Smart Software Solutions GmbH
- Version 3.5.19.70
- Windows based software

## PLC Logic (Main Program- PLC_PRG
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
-TON0 to TON4 - Motor1 running time
-TON5 - Doors openinng time
-TON6 - Open doors waiting time
-TON7 and TON8 - Doors closing time

PROGRAM BEHAVIOUR
The logic defines:
- How long the elevator opens doors (1 second)
- Door traveling time from one floor to another (8 seconds each)
- Door waiting time once at a floor (6 seconds)
- Buttons to press for floor selection
- Emergency button to press which shuts down the elevator completely
- Emergency buzzer which activates once emergency button is pressed


