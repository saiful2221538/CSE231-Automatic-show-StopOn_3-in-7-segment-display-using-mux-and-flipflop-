# Automatic Show "StopOn_3" in 7-Segment Display Using MUX and Flip-Flop

A digital logic circuit design that automatically cycles through and displays the alphanumeric sequence **"StopOn_3"** on a standard 7-Segment Display. Developed as a laboratory project for **CSE231 (Digital Logic Design)**, this project demonstrates the construction of a synchronous finite state machine (FSM) paired with data routing multiplexers in Logisim.

---

## 🛠️ Project Overview

The core objective of this project is to display an 8-character sequence (**S**, **t**, **o**, **p**, **O**, **n**, **_** [blank/dash], **3**) automatically and continuously upon receiving a clock signal.

The system architecture is split into two foundational components:

1. **The State Controller (Sequential Logic):** Uses sequential **J-K Flip-Flops** configured as a 3-bit modulo-8 synchronous counter to track individual character positions (`000` through `111`).
2. **The Data Router & Decoder (Combinational Logic):** Employs **Multiplexers (MUX)** that use the 3-bit state as select lines to route hardwired high/low constants corresponding to the active character's LED segments.

---

## 🏗️ Circuit Components & Architecture

The schematic is designed modularly within Logisim using the following core modules:

* **J-K Flip-Flops:** Three synchronous flip-flops interconnected with combinational logic gates to form a state counter that accurately transitions from $0 \rightarrow 7$ on each rising clock edge.
* **Multiplexers (4-to-1 / Multi-bit):** Responsible for evaluating the current state and selecting the pre-configured high/low inputs needed to light up the correct LEDs.
* **7-Segment Display:** A common-cathode or common-anode configured display component driven directly by the multiplexed lines to visualize individual alphanumeric shapes.
* **Clock Generator:** Provides the periodic signal that drives automatic state transitions and controls the character scroll frequency.

---

## 📊 State Table & Character Mapping

The 8 distinct states map directly to the corresponding alphanumeric patterns shown on the display:

| State (Binary) | State (Dec) | Character | Active 7-Segment Bars |
| --- | --- | --- | --- |
| `000` | 0 | **S** | a, c, d, f, g |
| `001` | 1 | **t** | d, e, f, g |
| `010` | 2 | **o** | c, d, e, g |
| `011` | 3 | **p** | a, b, e, f, g |
| `100` | 4 | **O** | a, b, c, d, e, f |
| `101` | 5 | **n** | c, e, g |
| `110` | 6 | **_** (Blank/Dash) | g (or all off) |
| `111` | 7 | **3** | a, b, c, d, g |

---

## 🚀 Getting Started

### Prerequisites

* **Logisim** (Version 2.7.1 or compatible versions like Logisim-Evolution).
* Java Runtime Environment (JRE) configured on your local operating system.

### Execution Steps

1. **Clone the Repository:**
```bash
git clone https://github.com/YOUR_USERNAME/Automatic-show-StopOn_3-in-7-segment-display-using-mux-and-flipflop.git
cd Automatic-show-StopOn_3-in-7-segment-display-using-mux-and-flipflop

```


2. **Open the Project in Logisim:**
* Launch Logisim.
* Navigate to `File -> Open` and select the file: `Automatic show StopOn_3 in 7-segment display using mux and flipflop.circ`.


3. **Run the Simulation:**
* Enable the system clock by navigating to `Simulate -> Simulation Enabled` (or press `Ctrl + E`).
* To automate the scroll sequence, go to `Simulate -> Ticks Enabled` (or press `Ctrl + K`).
* Adjust the speed by altering the frequency under `Simulate -> Tick Frequency`.

