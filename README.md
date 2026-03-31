# AlphaCatcher: 8086 Assembly Game

A real-time, interrupt-driven arcade game developed in **x86 Assembly Language (16-bit)**. The project demonstrates low-level hardware interaction, custom Interrupt Service Routine (ISR) hooking, and direct video memory manipulation.

## 🎮 Game Overview
**AlphaCatcher** is a fast-paced "falling alphabet" game. Random characters (A-Z) fall from the top of the screen at varying speeds. The player must move a paddle (box) at the bottom to catch them before they hit the ground.

### Features
* **Single Player & Multiplayer Modes:** Play solo or against a friend on the same keyboard.
* **Sprint Mechanic:** Hold the **Shift key** to move your paddle at **2x speed**.
* **Dynamic Difficulty:** The game automatically increases the falling speed of characters once the score reaches 8.
* **Real-time Stopwatch:** Tracks your survival time using the system timer.
* **Custom UI:** Includes a custom start menu and personalized "Desi" game-over messages.

---

## 🛠️ Technical Implementation
This project goes beyond simple loops and utilizes core computer architecture concepts:

* **ISR Hooking:** * Hooks **INT 08h (System Timer)** to handle concurrent movement of 5 different characters and the stopwatch without lagging the input.
    * Hooks **INT 09h (Keyboard)** for smooth, non-blocking player movement (allowing the paddle to move while characters are falling).
* **Direct Video Memory:** Writes directly to the `0xB800` segment for high-performance text-mode rendering.
* **Random Number Generation:** Uses the system clock (`INT 1Ah`) as a seed for a Linear Congruential Generator (LCG) to randomize character type and column position.
* **Memory Management:** Implements manual stack management and procedure calling conventions.

---

## 🚀 How to Run
To run this game, you will need an 8086 emulator like **DOSBox** and an assembler like **NASM**.

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/Ahmad-Yar-Khan/AlphaCatcher.git](https://github.com/Ahmad-Yar-Khan/AlphaCatcher.git)
    cd AlphaCatcher
    ```
2.  **Assemble the code:**
    ```bash
    nasm -f bin AlphaCatcher.asm -o AlphaCatcher.com
    ```
3.  **Run in DOSBox:**
    * Mount the folder in DOSBox.
    * Run `AlphaCatcher.com`.

---

## ⌨️ Controls
| Action | Key (Single Player) | Key (Multiplayer) |
| :--- | :--- | :--- |
| **Move Left** | Left Arrow | `A` (P1) / Left Arrow (P2) |
| **Move Right** | Right Arrow | `D` (P1) / Right Arrow (P2) |
| **Sprint (2x)** | Hold Shift | Hold Shift |
| **Quit Game** | `Esc` | `Esc` |
| **Restart** | `R` (at Game Over) | `R` (at Game Over) |

---

## 📜 Academic Context
Developed as part of the **Computer Organization and Assembly Language (COAL)** course at **FAST-NUCES Lahore**.
