# Dual-Servo-Motor-Control-with-Arduino
This project demonstrates how to control two servo motors simultaneously using an Arduino Uno.
One servo rotates from 0° to 180° while the other rotates in the opposite direction (180° to 0°) at the same time.

📝 Project Description
Two SG90 micro servo motors are connected to the Arduino.

Both servos are powered from the 5V and GND pins of the Arduino.

One servo is connected to PWM pin 9, and the other to PWM pin 10.

The Arduino sends PWM signals to rotate the servos in opposite directions.

📋 Components Required
✅ Arduino Uno
✅ USB cable for Arduino
✅ 2x SG90 Servo Motors
✅ Jumper Wires

🔌 Wiring
Servo	Signal Pin	VCC	GND
Servo 1	Pin 9	5V	GND
Servo 2	Pin 10	5V	GND

Connect the orange (signal) wire of Servo 1 to pin 9 on the Arduino.

Connect the orange (signal) wire of Servo 2 to pin 10.

Connect both red wires of the servos to 5V.

Connect both brown/black wires to GND.

Circuit Diagram
(Refer to the attached diagram for visual connection details.)

🖥️ Sample Arduino Code
cpp
نسخ
تحرير
#include <Servo.h>

Servo servo1;
Servo servo2;

void setup() {
  servo1.attach(9);
  servo2.attach(10);
}

void loop() {
  for (int pos = 0; pos <= 180; pos++) {
    servo1.write(pos);
    servo2.write(180 - pos);
    delay(15);
  }

  for (int pos = 180; pos >= 0; pos--) {
    servo1.write(pos);
    servo2.write(180 - pos);
    delay(15);
  }
}
🚀 How It Works
The Arduino uses the Servo library to control the PWM signal for each servo.

In the loop, Servo 1 moves from 0° to 180°, while Servo 2 moves from 180° to 0°, creating a mirrored motion.

The process repeats continuously.
