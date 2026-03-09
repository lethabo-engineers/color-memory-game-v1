# Color Memory Game — v1 (Arduino Mega)

A Simon-style color memory game built on an **Arduino Mega 2560** using **LEDs, buttons, and a buzzer**.  
The game generates a growing pattern using LEDs, and the player must repeat the sequence correctly using button inputs.

## What it does
- Generates a random LED sequence that grows each round
- Plays the sequence using LEDs
- Uses a buzzer for audio feedback
- Reads player input from buttons
- Ends the game when the player enters a wrong input

## Version info
- **v1:** Core gameplay using LEDs, buttons, and buzzer
- **v2:** LCD upgrade for score display, prompts, and clearer game feedback

## Documentation
- 📄 [Getting Started (wiring + pin map + notes)](Getting-started.md)
- 💻 [Arduino Code](./color-memory-game-v1.ino)

[Watch the demo on TikTok](https://www.tiktok.com/@l3thabo_o)
## Demo / Photos
![Final build](./images/final_build_v1.jpg)
<!-- ![Wiring overview](./images/wiring_overview.jpg) -->

## Hardware (v1)
- Arduino Mega 2560
- 4 LEDs
- 4 current-limiting resistors (e.g. 220Ω)
- 4 push buttons
- Passive buzzer
- Breadboard
- Jumper wires

## Future improvements
- Add an LCD screen

