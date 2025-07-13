## 🕒 Digital Clock on FPGA

This project implements a **Digital Clock** using **FPGA** and **Verilog HDL**. The clock displays **hours, minutes, and seconds** in real-time using either **7-segment displays**, **LCD**, or **LED arrays** depending on the FPGA board. It includes features like **reset**, **set time**, and accurate time counting based on the board’s clock frequency.

---

### 🔧 Features

* 24-hour format (HH\:MM\:SS)
* Time increment using 1 Hz clock pulse (from clock divider)
* Manual reset and set-time inputs
* Real-time update on 7-segment display or LEDs
* Synchronous design using finite state machines (FSM)

---

### 🧠 How It Works

* The system clock (usually 50MHz or 100MHz) is **divided down to 1Hz** using a **clock divider module**.
* Three counters are used to track **seconds**, **minutes**, and **hours**.
* Overflow from seconds increments the minute counter, and so on.
* Outputs are decoded and mapped to **7-segment displays** for visual output.

---

### 📁 Modules Overview

| Module              | Description                                |
| ------------------- | ------------------------------------------ |
| `clk_divider.v`     | Divides system clock to 1Hz                |
| `counter.v`         | Modular counters for sec, min, hour        |
| `display_decoder.v` | Converts binary to 7-segment format        |
| `digital_clock.v`   | Top-level module that integrates all logic |

---

### 🖥️ Hardware Requirements

* FPGA Board (e.g., Xilinx Spartan-6, Artix-7, or Basys 3)
* 7-Segment display (onboard or external)
* Buttons/switches for reset/set time
* Vivado / ISE / Quartus (based on your FPGA)

---

### 🧪 Simulation & Testing

* Simulated in **ModelSim/Vivado Simulator**
* Testbench included for verifying counter behavior
* Edge cases like 59 → 00 rollover handled

---

### 🧩 Possible Extensions

* AM/PM mode (12-hour format)
* Alarm feature
* LCD integration
* UART interface to update time via pc
