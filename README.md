# 4 LED Blinking Circuit with Push Button Toggle

A simple Arduino project built in TinkerCAD that controls 4 LEDs 
using a push button toggle. Press once to start blinking, press 
again to stop.

---

## 🔧 Components

| Component | Quantity |
|-----------|----------|
| Arduino Uno | 1 |
| LEDs (Red, Orange, Green, Blue) | 4 |
| 220Ω Resistors | 4 |
| Push Button | 1 |
| 10kΩ Resistor (pull-down) | 1 |
| Breadboard | 1 |
| Jumper Wires | Several |

---

## 📌 Pin Connections

| Component | Arduino Pin |
|-----------|-------------|
| Red LED | 13 |
| Orange LED | 12 |
| Green LED | 11 |
| Blue LED | 10 |
| Push Button | 2 |

---

## ⚡ How It Works

- Press the button **once** → all 4 LEDs start blinking
- Press the button **again** → all 4 LEDs stop
- Uses `millis()` instead of `delay()` so the button is 
  always responsive

---

## 🔌 Circuit Wiring

**LEDs:**
- Anode (long leg) → 220Ω resistor → Arduino pin
- Cathode (short leg) → GND rail

**Push Button:**
- Top-left leg → Arduino Pin 2
- Bottom-left leg → 5V
- Top-left leg row → 10kΩ resistor → GND

---

## 💻 Code

The main sketch is in `blinking_leds.ino`

Key concepts used:
- `pinMode()` — set pins as INPUT/OUTPUT
- `digitalWrite()` — turn LEDs on/off
- `digitalRead()` — read button state
- `millis()` — non-blocking timer for blinking
- Boolean toggle — tracks blinking state

---

## 🖥️ TinkerCAD Simulation



---

## 📸 Screenshot

![Circuit Screenshot](screenshot.png)

---

## 👤 Author

**Arthur NDORIMANA**  
CSA Student — Embedded Systems  
GitHub: [arthurndorimana397-a11y](https://github.com/arthurndorimana397-a11y)

---

## 📄 License

This project is open source and free to use.
