# arduino-pushbutton-led
# Arduino Pushbutton LED Control

A beginner-friendly Arduino project demonstrating how to control an LED using a momentary pushbutton.

The project was designed and simulated in Wokwi using an Arduino Uno, an LED, a current-limiting resistor, and a pushbutton.

## Project Overview

When the pushbutton is pressed, the Arduino detects the input and turns the LED ON. When the button is released, the LED turns OFF.

This project demonstrates the basic use of:

- Digital input
- Digital output
- Momentary pushbutton
- Internal pull-up resistor
- LED current limiting
- Arduino `digitalRead()` and `digitalWrite()`

## Components Used

| Component | Quantity |
|---|---:|
| Arduino Uno | 1 |
| Red LED | 1 |
| 220 Ω resistor | 1 |
| Momentary pushbutton | 1 |
| Breadboard | 1 |
| Jumper wires | As required |

## Circuit Connections

### LED

- Arduino digital pin 13 → 220 Ω resistor
- Resistor → LED anode
- LED cathode → GND

### Pushbutton

- One terminal of the pushbutton → Arduino digital pin 2
- Other terminal of the pushbutton → GND

The Arduino's internal pull-up resistor is enabled through `INPUT_PULLUP`.

## Working Principle

The pushbutton is configured as a digital input using the Arduino's internal pull-up resistor.

Therefore:

- Button released → input reads `HIGH`
- Button pressed → input reads `LOW`

The program turns the LED ON when the input is `LOW`.

## Author

**Deep Das**  
B.Tech ECE Student at Delhi Technological University (DTU)

[LinkedIn Profile](https://www.linkedin.com/in/deep-das-03ad4882/)

## Arduino Code

```cpp
const int ledPin = 13;
const int buttonPin = 2;

void setup() {
  pinMode(ledPin, OUTPUT);
  pinMode(buttonPin, INPUT_PULLUP);
}

void loop() {
  int buttonState = digitalRead(buttonPin);

  if (buttonState == LOW) {
    digitalWrite(ledPin, HIGH);
  } else {
    digitalWrite(ledPin, LOW);
  }
}
