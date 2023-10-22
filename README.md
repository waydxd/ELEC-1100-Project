# ELEC-1100-Project

# Line Follower Robot Car

This is a project that I did for ELEC 1100 course at HKUST. In this project, I built a line follower robot car using an Arduino Nano, three infrared sensors, and two DC motors. The robot car is able to follow a white line on a black surface. It does this by using infrared sensors to detect the line and adjusting the speed and direction of the motors using pulse-width modulation (PWM).

## Hardware Components

The hardware components that I used for this project are:

- Arduino Nano
- L293 motor driver IC
- Inverter
- 12V-to-5V regulator
- Resistors
- Capacitors
- Infrared sensors
- DC motors
- Wheels
- Battery
- Breadboard
- Jumper wires

## Circuit Diagram

The circuit diagram of the project is shown below:

![Circuit diagram]

## Logic Design

The logic design of the project is based on the following truth table and logic-flow chart:

| B_Sensor | L_Sensor | R_Sensor | countBumper | countWhite* | L_PWM | R_PWM | L_DIR | R_DIR |
|----------|----------|----------|-------------|-------------|-------|-------|-------|-------|
| 1        | 0        | 0        | 0           | 0           | 0     | 0     | 0     | 0     |
| 0        | 0        | 0        | 1           | 0           | 200   | 200   | 1     | 1     |
| 1        | 0        | 0        | 1           | 0           | 200   | 200   | 0     | 1     |
| 1        | 0        | 0        | 1           | 1           | 225   | 225   | 1     | 0     |
| 1        | 1        | 0        | 1           | 0           | 200   | 200   | 1     | 0     |
| 1        | 1        | 0        | 1           | 1           | 200   | 200   | 1     | 0     |
| 1        | 1        | 1        | 1           | 0           | 225   | 225   | 1     | 1     |
| 1        | 0        | 1        | 1           | 0           | 200   | 200   | 0     | 1     |
| 1        | 0        | 1        | 1           | 1           | 200   | 200   | 0     | 1     |
| 0        | 1        | 1        | 1           | 1           | 150/0^| 150/0^| 0     | 0     | 
| 1        | 1        | 1        | 1           | 1           | 225   | 225   | 1     | 1     |


