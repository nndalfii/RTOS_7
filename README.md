# STM32 FreeRTOS LED Control Project

This project demonstrates multitasking LED control using **STM32**, **FreeRTOS**, and GPIO. The project implements three tasks for controlling LEDs with different patterns, while ensuring safe access to shared resources using critical sections.

## Features
- **Green LED Task**: Toggles the green LED with a specific on/off delay pattern.
- **Red LED Task**: Toggles the red LED with a slower delay pattern.
- **Orange LED Task**: Flashes the orange LED rapidly.
- **Shared Resource Management**: Simulates safe access to a shared resource (`StartFlag`) using critical sections (`taskENTER_CRITICAL()` and `taskEXIT_CRITICAL()`).

## Hardware Requirements
- **Microcontroller**: STM32 (e.g., STM32F103, STM32F4xx).
- **LEDs**:
  - Green: Connected to `PA0`.
  - Red: Connected to `PA1`.
  - Blue (shared resource indicator): Connected to `PA2`.
  - Orange: Connected to `PA3`.
- **Power Supply**: Ensure appropriate power for the microcontroller (3.3V or 5V).

## Software Requirements
- **IDE**: STM32CubeIDE or equivalent.
- **STM32 HAL Library**: For peripheral drivers.
- **FreeRTOS**: For real-time task scheduling.

## Project Overview
1. **Critical Section Simulation**:  
   A shared variable (`StartFlag`) is used to simulate a shared resource. Critical sections are employed to avoid conflicts during read/write operations. If a conflict occurs, the blue LED turns on to signal contention.

2. **Task Descriptions**:
   - **Green LED Task**:
     - Turns the green LED on.
     - Accesses the shared resource.
     - Turns the LED off after 200 ms, then delays for 200 ms.
   - **Red LED Task**:
     - Turns the red LED on.
     - Accesses the shared resource.
     - Turns the LED off after 550 ms, then delays for 550 ms.
   - **Orange LED Task**:
     - Toggles the orange LED every 50 ms for a rapid flashing effect.

## How to Use
1. Clone the repository and open the project in **STM32CubeIDE**.
2. Configure the clock settings and GPIO pins as per the code.
3. Compile and flash the program onto the STM32 microcontroller.
4. Observe the LED patterns:
   - Green LED toggles with 200 ms on/off delays.
   - Red LED toggles with 550 ms on/off delays.
   - Orange LED flashes rapidly at 50 ms intervals.
   - Blue LED lights up if resource contention occurs.




https://github.com/user-attachments/assets/904b3f04-1552-4480-804a-1d0b49dfae8f

