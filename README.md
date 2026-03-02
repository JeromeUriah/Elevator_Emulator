-- Elevator Emulator --

An embedded C elevator controller/emulator built for the AVR platform. The project drives an LED matrix “elevator shaft” display, accepts button + serial inputs to select destination floors, and demonstrates timer-driven state updates and simple direction indication. :contentReference[oaicite:0]{index=0}

-- Overview --
This repository contains a small elevator simulation that:
- Shows a splash/start screen and begins when the user presses a button or sends `s`/`S` over serial. :contentReference[oaicite:1]{index=1}
- Lets users select floors via IO-board buttons (BUTTON0–BUTTON3) or serial keys `0`–`3`. :contentReference[oaicite:2]{index=2}
- Moves the elevator toward the destination in timed steps and redraws the elevator position on the LED matrix. :contentReference[oaicite:3]{index=3}
- Indicates direction (Up/Down/Stationary) via output lines (PORTA) and terminal printing. :contentReference[oaicite:4]{index=4}

-- Features --
- 4-floor model (Floor 0–3) rendered on an LED matrix :contentReference[oaicite:5]{index=5}
- Button and serial control for destination selection (`0`–`3`) :contentReference[oaicite:6]{index=6}
- Start screen animation and terminal banner output :contentReference[oaicite:7]{index=7}
- Speed toggle via an input pin (PD2) to change update interval (fast/slow) :contentReference[oaicite:8]{index=8}
- Simple “traveller” marker logic (one traveller at a time) :contentReference[oaicite:9]{index=9}

-- Controls -- 

### Start
- Press any button **or**
- Send `s` / `S` over serial to begin :contentReference[oaicite:10]{index=10}

### Select destination floor
- Buttons: `BUTTON0` → Floor 0, `BUTTON1` → Floor 1, `BUTTON2` → Floor 2, `BUTTON3` → Floor 3 :contentReference[oaicite:11]{index=11}  
- Serial: type `0`, `1`, `2`, or `3` :contentReference[oaicite:12]{index=12}

### Speed mode
- The update interval changes based on the state of input pin **PD2** (checked via `PIND2`). :contentReference[oaicite:13]{index=13}

## Build and Flash

This repo includes an AVR project file (`Assignment2.cproj`) for IDE-based builds/flashing. :contentReference[oaicite:14]{index=14}

## Repository Contents

Key files:
- `Elevator-Emulator.c` — main elevator controller logic (display, movement, input handling) :contentReference[oaicite:16]{index=16}
- `display.*`, `ledmatrix.*`, `buttons.*`, `serialio.*`, `terminalio.*`, `timer0.*`, `spi.*` — hardware abstraction modules and utilities :contentReference[oaicite:17]{index=17}
- `Assignment2.cproj` / `Assignment2.componentinfo.xml` — project configuration :contentReference[oaicite:18]{index=18}
