# Project 1: Color Memory Game (Arduino Mega) — Build Notes

## Build

## Notes
We are building a Simon-style color memory game on an Arduino Mega. 
This doc covers the full hardware setup, pin mapping, and how the code is structured (v1 LEDs + buttons, v2 adds an LCD).

---
## Hardware Overview
**Main board:** Arduino Mega 2560  
**Inputs:** Push buttons (player input)  
**Outputs:** LEDs (pattern display)  
**v2 upgrade:** 16x2 LCD (score + prompts)

---

## Pin Map (v1)
LED pins:
- LED1 (Red)  -> D2
- LED2 (Green)-> D3
- LED3 (Blue) -> D4
- LED4 (Yellow)-> D5

Button pins (recommended: INPUT_PULLUP):
- BTN1 -> D6
- BTN2 -> D7
- BTN3 -> D8
- BTN4 -> D9

Power:
- 5V  -> breadboard + rail (if needed)
- GND -> breadboard - rail (common ground)

> Update these pin numbers to match your actual wiring.

---

## Wiring Guide

### LEDs
For each LED:
- **Anode (long leg)** -> Arduino pin (D2–D5)
- **Cathode (short leg)** -> **220Ω resistor** -> GND

### Buttons (INPUT_PULLUP)
For each button:
- One side -> **GND**
- Other side -> Arduino pin (D6–D9)

In code:
- `pinMode(buttonPin, INPUT_PULLUP);`
- **Pressed = LOW**, **Released = HIGH**

---

## How the Game Logic Works (v1)
- The Arduino stores a sequence (e.g., `[2, 0, 3, 1]`)
- Each round it adds one new random step
- LEDs play the full sequence
- Player repeats the sequence via buttons
- If wrong input -> game over; score = last correct round

---

## Code Structure (suggested)
- `setup()` initializes pins + resets game state
- `loop()` runs the main game state machine:
  - SHOW_PATTERN
  - READ_INPUT
  - CHECK_INPUT
  - NEXT_ROUND / GAME_OVER

---

## Upload & Test
1. Upload the `.ino` file
2. Confirm each LED turns on
3. Confirm each button press registers correctly
4. Start game and test sequence playback + input checking

---

## Troubleshooting

### LEDs don’t light
- Check LED polarity (anode/cathode)
- Confirm resistors are in series
- Confirm you’re using the correct pin numbers

### Buttons trigger randomly / always pressed
- Make sure you are using `INPUT_PULLUP`
- Button must connect to **GND** (not 5V) when pressed

---
