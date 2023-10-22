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
*countWhite only affect the behavior of motor when both L&R_sensors sense white
^ 150 for few milliseconds, then 0


## Code

The code for the project is written in Arduino and can be found in the file `line_follower.ino`. The code uses analogWrite() to generate PWM signals on certain pins, digitalRead() to read the sensor values, and digitalWrite() to set the direction pins. The code also uses if-else statements and delay() to control the logic and timing of the car movement.

## Debugging Report

During the project, I encountered many bugs and defects that affected the performance of my robot car. In this part, I will describe two cases of bugs that I faced and how I solved them.

The first bug was related to the infrared sensors that detect the line on the mat. I found that the sensors were very fragile and prone to malfunctioning. Sometimes they would stop working after my car crashed into a wall, and sometimes they would give wrong readings of the reflectance of the surface. For example, they would detect a black surface as white and vice versa. I suspected that the quality of the sensors was poor and that the circuit was quite unstable. The shaking of the car when moving might have caused some loose connections or damage to the sensors. To fix this bug, I had to replace the sensors many times until I found some reliable ones that worked consistently.

The second bug was related to the wheels that drive the car. I found that if I did not screw the wheels tightly enough, they would affect the car movement. For example, when the car sensed a horizontal white line, it was supposed to change direction by reversing the polarity of the motors. However, if the wheels were loose, they would not change direction immediately and would keep moving in the original direction for a while. This would cause the car to go out of track and miss the line. At first, I thought this bug was due to the sensors not sensing properly and I changed them many times, but it did not help. Finally, I realized that it was the wheels that were causing the problem. To fix this bug, I had to screw the wheels very hard and make sure they were aligned with the motors.

## Result & Conclusion

The result of the project was that I successfully built a line follower robot car that could follow a white line on a black surface. The car could handle different scenarios on the mat, such as straight lines, curves, corners, T-lines, and finish lines. The car could also switch between left and right turns when encountering a horizontal white line by using a variable called countWhite. The car could also stop or change direction when reaching a finish line by using a delay() function.

The conclusion of the project was that I learned a lot from this project. I learned how to use PWM to control the speed and direction of a DC motor, how to use infrared sensors to detect a line on a mat, how to use an inverter and an H-bridge to switch the polarity of the voltage applied to the motor terminals, how to write simple and precise code for different scenarios on

