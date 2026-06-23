# Raspberry Pi Pico W Projects using C SDK

A collection of Raspberry Pi Pico W projects developed using the Raspberry Pi Pico Software Development Kit (C SDK). This repository covers Pico SDK installation, LED traversal projects, user-controlled LEDs using bitwise operators, and Picotool utilities.

## Team Members

- Karthick A
- Luckshana V R
- Shree Subi G
- Janasruthika P R

## Guided By

Durai P S

## Mentor

Daniel Raj A

---

# Repository Contents

## 1. Pico SDK Installation and Compilation

This project explains the complete setup process for Raspberry Pi Pico W development.

### Topics Covered

- Installing Pico SDK
- Cloning pico-sdk and pico-examples
- Installing dependencies
- Configuring environment variables
- Building programs using CMake
- Generating UF2 files
- Flashing programs
- Troubleshooting common errors

### Commands Used

```bash
git clone https://github.com/raspberrypi/pico-sdk.git

git clone https://github.com/raspberrypi/pico-examples.git

export PICO_SDK_PATH=/path/to/pico-sdk

cmake ..

make
```

---

## 2. LED Traverse Left to Right

Sequentially turns ON 8 LEDs from left to right using GPIO0-GPIO7.

### Concepts

- GPIO initialization
- Bitwise operations
- GPIO masking
- Delay generation

---

## 3. LED Traverse Right to Left

Sequentially turns ON 8 LEDs from right to left.

### Concepts

- GPIO configuration
- Bit shifting
- LED animation

---

## 4. User Selected LED Blink using Bitwise Operators

Allows users to select LEDs (1-8) via USB serial communication.

### Features

- Interactive LED control
- User input through terminal
- Bitwise operations

---

## 5. Picotool Commands and Usage

Demonstrates firmware management using Picotool.

### Commands Covered

- picotool info
- picotool config
- picotool load
- picotool save
- picotool verify
- picotool reboot
- picotool version

---

# Hardware Requirements

- Raspberry Pi Pico W
- Breadboard
- 8 LEDs
- 220Ω Resistors
- Jumper wires
- USB cable

---

# Software Requirements

- Ubuntu/Linux
- Git
- CMake
- ARM GNU Toolchain
- Build Essential
- Newlib ARM
- Minicom
- Picotool

Install dependencies:

```bash
sudo apt update

sudo apt install cmake gcc-arm-none-eabi \
build-essential \
libnewlib-arm-none-eabi \
minicom
```

---

# Clone Pico SDK

```bash
mkdir pico

cd pico

git clone https://github.com/raspberrypi/pico-sdk.git --branch master

cd pico-sdk

git submodule update --init

cd ..

git clone https://github.com/raspberrypi/pico-examples.git --branch master
```

---

# Build a Project

```bash
mkdir build

cd build

cmake ..

make
```

If any CMake errors occur:

```bash
cmake --version

sudo apt remove cmake

sudo snap install cmake --classic
```

For Pico W:

```bash
cmake .. -DPICO_BOARD=pico_w
```

---

# Flashing the Pico W

1. Press and hold the BOOTSEL button.
2. Connect the Pico W via USB.
3. Release BOOTSEL.
4. Copy the generated UF2 file.

```bash
cp project_name.uf2 /media/$USER/RPI-RP2/
```

---

# Project Structure

```text
Raspberry-Pi-PicoW-CSDK/
│
├── Pico_SDK_Installation/
│   └── Documentation.pdf
│
├── Traverse_Left_to_Right/
│   ├── led_traverse.c
│   └── CMakeLists.txt
│
├── Traverse_Right_to_Left/
│   ├── led_traverse.c
│   └── CMakeLists.txt
│
├── User_Selected_LED_Blink/
│   ├── main.c
│   └── CMakeLists.txt
│
├── Picotool_Guide/
│   └── Documentation.pdf
│
└── README.md
```

---

# Learning Outcomes

- Raspberry Pi Pico W architecture
- Embedded C programming
- Pico SDK setup
- GPIO programming
- Bitwise operators
- Serial communication
- Firmware flashing
- Picotool utilities
- Troubleshooting build errors

---

# References

- https://github.com/raspberrypi/pico-sdk
- https://github.com/raspberrypi/pico-examples
- https://github.com/raspberrypi/picotool
- https://www.raspberrypi.com/documentation/microcontrollers/
- https://datasheets.raspberrypi.com/picow/pico-w-datasheet.pdf
