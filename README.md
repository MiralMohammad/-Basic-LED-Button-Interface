
# 🔌 3-Button LED Controller with Arduino

This project is a simple and fun demonstration of how to control **three LEDs** using **three individual push buttons** with an Arduino UNO. Each button controls one LED independently.

![Circuit Diagram](./Screenshot%202025-07-24%20110948.png)

---

## 🧰 Components Used

- 1 × Arduino UNO
- 3 × LEDs (Red, Green, Blue)
- 3 × Push Buttons
- 3 × 220Ω Resistors (for LEDs)
- Breadboard
- Jumper Wires
- USB Cable (for uploading code and power)

---

## ⚙️ Circuit Description

Each button is connected to a **digital input pin** on the Arduino. When a button is pressed, it turns on a corresponding LED connected to a **digital output pin**.

| Button | LED  | Arduino Pins  |
|--------|------|----------------|
| 1      | Green | D2 (button), D8 (LED) |
| 2      | Blue  | D3 (button), D9 (LED) |
| 3      | Red   | D4 (button), D10 (LED) |

---

## 📜 Arduino Code

```cpp
// Pins for LEDs
const int led1 = 8;
const int led2 = 9;
const int led3 = 10;

// Pins for buttons
const int button1 = 2;
const int button2 = 3;
const int button3 = 4;

void setup() {
  // Set LED pins as output
  pinMode(led1, OUTPUT);
  pinMode(led2, OUTPUT);
  pinMode(led3, OUTPUT);

  // Set button pins as input with internal pull-up
  pinMode(button1, INPUT_PULLUP);
  pinMode(button2, INPUT_PULLUP);
  pinMode(button3, INPUT_PULLUP);
}

void loop() {
  // Check button 1
  if (digitalRead(button1) == LOW) {
    digitalWrite(led1, HIGH);
  } else {
    digitalWrite(led1, LOW);
  }

  // Check button 2
  if (digitalRead(button2) == LOW) {
    digitalWrite(led2, HIGH);
  } else {
    digitalWrite(led2, LOW);
  }

  // Check button 3
  if (digitalRead(button3) == LOW) {
    digitalWrite(led3, HIGH);
  } else {
    digitalWrite(led3, LOW);
  }
}
