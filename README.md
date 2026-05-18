# 🕹️ Game Console — STM32F401CC

A bare-metal embedded game console built on the **STM32F401CC** microcontroller, featuring two classic games: **Pac-Man** and **Ping Pong**. Written primarily in **ARM Assembly** with C, and developed using STM32CubeIDE.

---

## 🎮 Games

### 👾 Pac-Man
Navigate Pac-Man through a maze, eat all the dots, and avoid the ghosts. Classic arcade gameplay implemented directly on bare-metal hardware.

### 🏓 Ping Pong
A single-player paddle game where you bounce the ball past your opponent to score points.

---

## 📁 Repository Structure

```
Game-Console/
├── Inc/                              # Header files
├── Src/                              # C and Assembly source files
├── Startup/                          # STM32 startup assembly code
├── Debug/                            # Build output (debug binaries)
├── STM32F401CCUX_FLASH.ld            # Linker script for flash memory
└── Micro_Project_CubeIDE Debug.launch  # STM32CubeIDE debug configuration
```

---

## 🧰 Hardware Requirements

| Component | Details | Purpose |
|-----------|---------|---------|
| Microcontroller | STM32F401CC (BlackPill) | Main processing unit |
| Display | TFT LCD / OLED (SPI or GPIO) | Game rendering |
| Input Buttons | Push buttons (GPIO) | Player controls |
| Power Supply | USB (5V) or 3.3V regulated | Power |
| ST-Link V2 | Debugger/Programmer | Flashing & debugging |

> **Note:** Update the pin configurations in the header files under `Inc/` to match your exact hardware wiring.

---

## 💻 Software Requirements

- [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html) (v1.10+)
- ARM GCC Toolchain (bundled with STM32CubeIDE)
- ST-Link drivers ([download here](https://www.st.com/en/development-tools/stsw-link009.html))

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/MohamedSobh032/Game-Console.git
```

### 2. Import into STM32CubeIDE

```
File → Import → Existing Projects into Workspace
→ Select the cloned folder → Finish
```

### 3. Build the Project

```
Project → Build All  (or Ctrl+B)
```

The compiled binary will appear in the `Debug/` folder.

### 4. Flash to the Board

Connect your ST-Link V2 to the STM32F401CC and run:

```
Run → Debug  (or press F11)
```

Or flash directly using the ST-Link Utility:
```
Target → Program & Verify → Select Debug/*.elf → Start
```

---

## 🔌 Wiring Overview

### ST-Link V2 → STM32F401CC (BlackPill)
```
ST-Link   → STM32
SWDIO     → DIO  (PA13)
SWCLK     → CLK  (PA14)
GND       → GND
3.3V      → 3.3V
```

### Buttons (Player Controls)
```
Button    → GPIO Pin (configure in Inc/)
UP        → e.g. PA0
DOWN      → e.g. PA1
LEFT      → e.g. PA2
RIGHT     → e.g. PA3
```

> Refer to the pin definitions in `Inc/` for the actual assignments used in this project.

---

## 🛠️ Tech Stack

- **Language**: ARM Assembly (94%), C
- **Platform**: STM32F401CC (ARM Cortex-M4, 84 MHz)
- **IDE**: STM32CubeIDE
- **Build**: Make + ARM GCC
- **Linker Script**: `STM32F401CCUX_FLASH.ld` (bare-metal, no OS)
- **Programming**: ST-Link V2
