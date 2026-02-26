# STM32 Voting System

## Project Overview
A microcontroller-based voting system implemented on an ARM Cortex-M4 STM32 platform. The system records votes for two candidates using two push-button inputs and displays results in real time on dual 7-segment displays. The design demonstrates GPIO configuration, interrupt-driven processing, and direct register-level programming.

---

## Key Features
- Real-time vote counting using push buttons  
- Interrupt-driven input handling
- Dual 7-segment display output for vote visualization  
- Reset to clear vote counts  

---

## Hardware Components
- STM32 Nucleo-64 (F446RE) 
- Push Buttons ×3 (Vote A, Vote B, Reset)  
- Two 7-Segment Displays (Common Cathode)  
- Breadboard and Resistors  
- USB Programming Interface  

---

## Pin Configuration

| Pin | Function |
|-----|---------|
| PA0 | Reset Button |
| PA1 | Vote for Candidate B |
| PA4 | Vote for Candidate A |
| PB0–PB7 | 7-Segment Display A |
| PC0–PC7 | 7-Segment Display B |

---

## System Operation

### Vote Counting
- Push buttons act as input devices connected to GPIO pins.  
- When a vote button is pressed, an external interrupt is triggered.  
- The microcontroller increments the corresponding vote counter.  
- The updated vote value is displayed immediately on the 7-segment display.

### Reset
- When the reset button is pressed, an interrupt resets both vote counters to zero.  
- The displays update to show cleared results.

---

## Software Description
The system is implemented using **bare-metal embedded C** with direct register-level configuration of STM32 peripherals.

### Main Processes
- GPIO configuration for input and output control  
- External interrupt (EXTI) handling  
- Vote counter management  
- 7-segment display encoding  
- Software debouncing for input stability  

---

## Initialization
During system startup:
- Vote counters initialize to zero  
- Displays show default value  
- GPIO and interrupt systems are configured  
- System waits for hardware interrupts (push buttons)  

---

## Development Environment
- Embedded C  
- STM32CubeIDE  
- ARM Cortex-M4

---

## Author
Yap Boon Jie  
Electronics Engineering Student  
Universiti Teknologi Malaysia
