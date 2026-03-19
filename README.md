# Arduino LED Fade using PWM

## Overview
This project demonstrates how to control the brightness of an LED using Pulse Width Modulation (PWM) on an Arduino Uno. Instead of simply turning the LED ON or OFF, the brightness is gradually increased and decreased to create a smooth fading effect.

## Context
This project was developed as part of a laboratory experiment for the course *Electronics Communication Simulation Workshop*, to gain hands-on experience with basic embedded systems and hardware interfacing.

## Objective
To understand how PWM can be used to simulate analog output using digital pins and control the intensity of an LED.

## Components Used
- Arduino Uno
- LED
- Resistors (~220Ω equivalent)
- Breadboard
- Jumper wires

## Working Principle
PWM (Pulse Width Modulation) is used to vary the effective voltage supplied to the LED:
- Higher duty cycle → LED appears brighter  
- Lower duty cycle → LED appears dimmer  

The Arduino rapidly switches the output between HIGH and LOW, and by adjusting the duration of the HIGH signal, the brightness of the LED is controlled.

## Implementation
- The LED is connected to a PWM-enabled pin (Pin 9)
- analogWrite() is used to vary brightness from 0 to 255
- Two loops are used:
  - One to increase brightness (fade in)
  - One to decrease brightness (fade out)

## Code
int ledPin = 9;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  for (int brightness = 0; brightness <= 255; brightness++) {
    analogWrite(ledPin, brightness);
    delay(10);
  }

  for (int brightness = 255; brightness >= 0; brightness--) {
    analogWrite(ledPin, brightness);
    delay(10);
  }
}

## Circuit Setup
- Connect LED anode to pin 9  
- Connect cathode to resistor  
- Connect resistor to GND  

Note: Equivalent resistance (~220Ω) was achieved using multiple resistors in parallel.

## Output
The LED gradually increases in brightness and then decreases, creating a continuous fade in and fade out effect.

## Learning Outcomes
- Understanding PWM and duty cycle  
- Basics of embedded programming  
- Hardware interfacing using Arduino  
- Practical exposure to breadboard prototyping  

## Future Improvements
- Control brightness using a potentiometer  
- Add multiple LEDs with different patterns  
- Implement button-based control  

---
