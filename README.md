# Whack-A-Mole FPGA Game

## EEGR 211 Digital Logic Design Project

### Overview

This project is a hardware-based implementation of the classic **Whack-A-Mole** arcade game using an FPGA development board. The game was designed as part of **EEGR 211** and demonstrates the use of digital logic, finite state machines, counters, timers, and user input handling in an embedded hardware environment.

The objective of the game is simple:
A “mole” appears in one of several positions, and the player must press the corresponding button before the timer expires. Successful hits increase the score, while missed moles or incorrect inputs reduce remaining lives or end the game.

---

# Features

* Randomized mole generation
* Real-time player input detection
* Score tracking
* Countdown/game timer
* LED or 7-segment display output
* Game-over state
* Fully implemented on FPGA hardware
* Written in Verilog/VHDL *(replace with whichever you used)*

---

# Hardware Used

* FPGA Development Board: *(example: Nexys 4 DDR / Basys 3 / DE10-Lite)*
* Pushbuttons or switches for player input
* LEDs and/or 7-segment displays for output
* Clock source from onboard oscillator

---

# Project Structure

```text
/project-root
│
├── src/
│   ├── top_module.v
│   ├── game_fsm.v
│   ├── random_generator.v
│   ├── score_counter.v
│   ├── timer.v
│   └── display_driver.v
│
├── constraints/
│   └── board_constraints.xdc
│
├── simulation/
│   └── testbench.v
│
└── README.md
```

---

# How the Game Works

1. The game starts after reset or button press.
2. A mole appears at a random position.
3. The player presses the matching button.
4. If the correct button is pressed before timeout:

   * Score increases
   * New mole is generated
5. If the player misses:

   * Life decreases or timer continues
6. The game ends when:

   * Timer reaches zero, or
   * Player runs out of lives

---

# Design Components

## Finite State Machine (FSM)

The game logic is controlled using an FSM with states such as:

* `IDLE`
* `START`
* `MOLE_ACTIVE`
* `HIT`
* `MISS`
* `GAME_OVER`

---

## Random Mole Generator

A pseudo-random generator selects which mole position becomes active during gameplay.

---

## Timer Module

A clock divider slows the FPGA clock into human-readable timing intervals for gameplay speed.

---

## Score Counter

Tracks successful hits and displays the player’s score using LEDs or seven-segment displays.

---

# Simulation

Simulation testbenches were used to verify:

* Correct state transitions
* Button input handling
* Timer functionality
* Score increment logic

Example tools:

* Vivado Simulator
* ModelSim

---

# Building and Running

## 1. Open the Project

Open the project in:

* Xilinx Vivado
* Quartus Prime
* *(whichever software you used)*

---

## 2. Synthesize the Design

Run:

* Synthesis
* Implementation
* Bitstream Generation

---

## 3. Program the FPGA

Upload the generated bitstream to the FPGA board using the onboard programmer.

---

# Learning Outcomes

Through this project, we learned:

* FPGA design workflow
* Hardware description languages
* Finite State Machine implementation
* Clock management
* Hardware debugging and testing
* Real-time digital system design

---

# Future Improvements

* VGA display support
* Sound effects using PWM audio
* Higher difficulty levels
* Faster mole generation over time
* Multiplayer support

---

# Authors

Mitko Georgiev
EEGR 211 – Digital Logic Design

---

# License

This project was created for educational purposes as part of coursework at Morgan State University.
Owned by Mitko Georgiev.
