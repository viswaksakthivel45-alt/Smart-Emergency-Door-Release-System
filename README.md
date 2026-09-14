# Smart-Emergency-Door-Release-System
Arduino-based emergency door release system using temperature detection 
# Smart Emergency Door Release System

An Arduino-based emergency door release system using temperature detection and manual emergency activation.

## Project Overview

The Smart Emergency Door Release System is designed to improve safety by automatically releasing a door during an emergency condition.

A TMP36 temperature sensor is used to monitor the temperature. When the temperature reaches or exceeds 50°C, the system detects a high-temperature condition. A manual emergency pushbutton is also provided for immediate emergency activation.

The system uses 74HC08 AND and 74HC32 OR logic gates to implement the emergency decision logic. When an emergency is detected, the servo motor opens the door, the buzzer is activated, and the red LED turns ON. During normal conditions, the green LED remains ON and the door stays closed.

The project is designed and tested using Arduino and can be simulated using Tinkercad.

## Objectives

- Detect high-temperature emergency conditions.
- Provide manual emergency activation.
- Automatically open the door during an emergency.
- Activate an audible alarm during an emergency.
- Provide visual indication using red and green LEDs.
- Demonstrate AND and OR logic gate operations.
- Implement the system using Arduino programming.

## Components Used

- Arduino UNO
- TMP36 Temperature Sensor
- 74HC08 AND Gate IC
- 74HC32 OR Gate IC
- Servo Motor
- Emergency Pushbutton
- Buzzer
- Red LED
- Green LED
- 330 Ω Resistors
- 10 kΩ Resistor
- Breadboard
- Jumper Wires

## Working Principle

### Normal Condition

When the temperature is below 50°C and the emergency button is not pressed:

- Green LED: ON
- Red LED: OFF
- Buzzer: OFF
- Door: CLOSED

### Emergency Condition

When the temperature reaches or exceeds 50°C, or the emergency button is pressed:

- Green LED: OFF
- Red LED: ON
- Buzzer: ON
- Door: OPEN

## Logic Used

The emergency logic is:

```text
FIRE_ALARM = SYSTEM_ARMED AND HIGH_TEMPERATURE

EMERGENCY = FIRE_ALARM OR MANUAL_EMERGENCY
