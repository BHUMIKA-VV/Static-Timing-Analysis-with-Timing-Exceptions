# Static Timing Analysis with Timing Exceptions

## 📌 Overview

This project demonstrates **Static Timing Analysis (STA)** on a synthesized RTL design using **Synopsys Design Compiler and PrimeTime**. It focuses on applying **timing exceptions** such as *false paths* and *case analysis* to study their impact on timing behavior.

---

## 🧩 Design Description

The design consists of:

* Multiplexers
* Half Adder
* AND gates

### Functional Logic:

* **E = A + B**
* **F = B + D (when S = 0)**
* **F = C + D (when S = 1)**

---

## ⚙️ Tools & Technologies

* **Verilog HDL** – RTL design (`design.v`)
* **Design Compiler** – Synthesis (`design_mapped.v`)
* **PrimeTime** – Static Timing Analysis
* **TCL Scripts** – Timing constraints and exceptions

---

## 🏗️ Design Flow

1. RTL design implemented in Verilog (`design.v`)
2. Synthesized using Design Compiler → generated gate-level netlist (`design_mapped.v`)
3. Imported netlist into PrimeTime
4. Applied timing constraints and exceptions using TCL scripts
5. Performed timing analysis and observed results

---

## 🌡️ Operating Conditions

* Voltage: **0.95 V**
* Temperature: **125°C**
* Analysis Mode: **On-Chip Variation (OCV)**

👉 Represents **worst-case timing conditions**

---

## ⏱️ Timing Scripts

### 🔹 Case Analysis (`case_analysis.tcl`)

* Used to fix input signals to constant values
* Helps analyze specific functional modes
* Command used:

  ```
  set_case_analysis
  ```

---

### 🔹 False Path (`false_path.tcl.tcl`)

* Defines paths that are excluded from timing analysis
* Prevents unnecessary timing checks on non-critical paths
* Command used:

  ```
  set_false_path
  ```

---

### 🔹 Virtual Clocks (`virtualClocks.tcl`)

* Defines separate timing domains using virtual clocks:

  * clk1 → A to E, C to E
  * clk2 → B to F, D to F

👉 Helps in analyzing independent timing paths

---

## 📊 Key Observations

* Timing constraints significantly affect timing reports
* **Case analysis** simplifies logic paths
* **False paths** are excluded from timing checks but do not change physical delays
* Virtual clocks help model multiple timing domains

---

## 📁 Project Structure

```
StaticTimingAnalysis/
│── design.v
│── design_mapped.v
│── case_analysis.tcl
│── false_path.tcl.tcl
│── virtualClocks.tcl
│── Schematic.PNG
│── README.md
```

---

## 🧠 Key Learnings

* Basics of **Static Timing Analysis (STA)**
* Understanding of:

  * Setup and Hold timing
  * Slack and critical paths
* Practical usage of:

  * `set_false_path`
  * `set_case_analysis`
* Exposure to **industry tools (Design Compiler & PrimeTime)**

---

## 🚀 Conclusion

This project provides hands-on experience with **timing analysis and constraint handling**, essential for ASIC design and physical design roles. It demonstrates how timing exceptions influence analysis and optimization in digital circuits.

---
