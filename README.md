# Starbie ⭐
First PCB design

A tiny motion-controlled desktop pet, like a mini Tamagotchi. Starbie lives on a custom PCB with a small OLED screen for its face, two RGB LEDs that show its mood, and a motion sensor that wakes it up when you shake or move it.

<img width="1154" height="647" alt="Screenshot from 2026-10-11 10-07-18" src="https://github.com/user-attachments/assets/7ce3e1ea-ba3e-41ea-80d2-8956c55cc183" />

## What it does

- **Shake to wake:** the MPU6050 motion sensor detects movement and wakes Starbie up.
- **Sleeps when idle:** after a while with no motion, Starbie goes to sleep and shows a sleeping face.
- **Shows emotions:** the OLED shows faces with eyes and a mouth (happy, sad, sleepy and more).
- **Mood lights:** two RGB LEDs change colour with its emotion, for example red when angry and green when something good happens.
- **Two buttons:** used to interact with Starbie.
- **Planned:** a sleepy yawn before it falls asleep, extra faces, and a hunger/boredom meter.

## Why I made it
I wanted to build a tiny desktop pet that feels alive, a little like a Tamagotchi. Instead of pressing buttons all the time, Starbie reacts to motion: you shake it to wake it up, and it falls asleep when you leave it alone. I also wanted to design the hardware myself, from the schematic to the cute board shape, and to learn KiCad, Git and GitHub along the way.

## What makes it different

- Designed my own board shape instead of copying an existing design.
- Custom face and emotion system with LED colours tied to mood.

## Hardware

| Part | Purpose |
|---|---|
| Seeed Studio XIAO ESP32-C3 | Microcontroller |
| MPU6050 | Motion sensing (shake to wake) |
| 0.96" 128x64 I2C OLED | Shows Starbie's face |
| 2 x push buttons (SW1, SW2) | User input |
| 2 x RGB LEDs (D1, D2) | Mood lights |

Full parts list with prices: see [`bom.csv`](bom.csv).

## Design files

Everything was designed in **KiCad**.

| File | What it is |
|---|---|
| `starbie.kicad_sch` | Schematic |
| `starbie.kicad_pcb` | PCB layout |
| `starbie.kicad_pro` | KiCad project file |

### Schematic

<img width="985" height="704" alt="Screenshot from 2026-10-09 10-24-23" src="https://github.com/user-attachments/assets/fef5e116-df08-4709-9c75-8300fa526515" />

### 3D view

<img width="1154" height="647" alt="Screenshot from 2026-10-11 10-07-18" src="https://github.com/user-attachments/assets/7ce3e1ea-ba3e-41ea-80d2-8956c55cc183" />

## How it works

1. The XIAO ESP32-C3 reads motion data from the MPU6050 over I2C.
2. A shake wakes Starbie. If there is no motion for a set time, it goes to sleep.
3. The OLED (also on I2C) draws a face for the current mood.
4. The two LEDs change colour to match the mood.


## Build it yourself

1. Open `starbie.kicad_pro` in KiCad.
2. Order the PCB using the fabrication files (Gerbers) if included, and buy the parts in the BOM.
3. Solder the components onto the board.
4. Flash the firmware to the XIAO ESP32-C3. [Add firmware instructions and library list.]

## Project log

See [`JOURNAL.md`](JOURNAL.md) for my build journal and time tracking.

## What I learned

- Designing a schematic and PCB layout in KiCad
- Using AI models as a build partner
- Using Git and GitHub to version my hardware project

## Status

- [x] Schematic
- [ ] PCB routing (finishing the last connections)
- [x] BOM
- [ ] Firmware
- [ ] Built and tested
