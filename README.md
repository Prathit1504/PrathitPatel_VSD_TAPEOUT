# RISC-V SoC Design & Tapeout Journey
### Week 0: Foundation & Toolchain Setup

![Status](https://img.shields.io/badge/Week%200-Complete-green)
![Tools](https://img.shields.io/badge/EDA%20Tools-Verified-blue)
![Platform](https://img.shields.io/badge/Platform-OpenLane%20VDI-lightgrey)

This repository documents my 20-week journey through the RISC-V Reference SoC Tapeout Program. This initial entry covers the foundational setup, including understanding the complete chip design flow and verifying the entire Electronic Design Automation (EDA) toolchain.

<br>

<details>
  <summary><strong>Table of Contents (Click to Expand)</strong></summary>
  
  - [🎯 Week 0 Mission](#-week-0-mission)
  - [🗺️ The Chip Blueprint: SoC Design Flow](#️-the-chip-blueprint-soc-design-flow)
  - [🛠️ The Digital Workbench: Toolchain Verification](#️-the-digital-workbench-toolchain-verification)
  - [💡 Real-World Impact: Potential Applications](#-real-world-impact-potential-applications)
  - [🏆 Week 0 Debrief: Achievements & Learnings](#-week-0-debrief-achievements--learnings)
  - [📓 Field Notes: Troubleshooting & Fixes](#-field-notes-troubleshooting--fixes)
  - [➡️ Next Steps](#️-next-steps)

</details>

---

### ## 🎯 Week 0 Mission

The primary goal for this week was to prepare the entire development environment and build a strong conceptual understanding of the journey from code to silicon.

- [x] **Understand the VLSI Lifecycle:** Grasp the complete RTL-to-GDSII flow.
- [x] **Configure the Environment:** Set up the OpenLane VDI and essential tools.
- [x] **Verify the Toolchain:** Confirm that all synthesis, simulation, and layout tools are operational.
- [x] **Explore Applications:** Research the practical use-cases for this RISC-V SoC.

---

### ## 🗺️ The Chip Blueprint: SoC Design Flow

The project follows a four-stage flow to transform an abstract idea into a physical chip targeting a **100-130MHz** frequency.

1.  **Stage O1/O2: Architectural Modeling**
    * This is the conceptual phase. We use C-models to define the chip's behavior and develop the core Register-Transfer Level (RTL) logic in Verilog that describes the hardware.

2.  **Stage O3: SoC Integration**
    * Here, we act as system integrators. The synthesized CPU core is combined with other crucial components like memory blocks (macros), analog circuits, and input/output pads (GPIOs) to form the complete System-on-Chip.

3.  **Stage O4: Physical Implementation**
    * This is where the design becomes physical. The automated flow handles **floorplanning**, **placement**, **clock tree synthesis**, and **routing** to create the final GDSII layout file—the blueprint that gets sent to the fabrication plant.

---

### ## 🛠️ The Digital Workbench: Toolchain Verification

A robust toolchain is critical. This section confirms the successful installation and operation of all necessary EDA software within the OpenLane VDI.

#### **Verification Command Log:**
This block confirms that all tools are installed and accessible from the command line.
<img width="1920" height="1080" alt="Screenshot (137)" src="https://github.com/user-attachments/assets/ef3fcefe-2f08-442f-bf4a-6731ea4c1e40" />
<img width="1920" height="1080" alt="Screenshot (139)" src="https://github.com/user-attachments/assets/6a331522-a4d5-4009-a8dd-2c93e3f84304" />
<img width="1920" height="1080" alt="Screenshot (138)" src="https://github.com/user-attachments/assets/fd97a7df-eab5-422f-95df-d301af513c10" />
<img width="1920" height="1080" alt="Screenshot (140)" src="https://github.com/user-attachments/assets/b4b19b41-a778-44d8-917f-07f58529ce8c" />
<img width="1920" height="1080" alt="Screenshot (141)" src="https://github.com/user-attachments/assets/918f5c7e-aa9a-49c2-82f7-262531b31387" />
<img width="1920" height="1080" alt="Screenshot (142)" src="https://github.com/user-attachments/assets/bd8f82fb-9dd4-401b-9f2c-bb270d438bd2" />

<img width="1920" height="1080" alt="Screenshot (143)" src="https://github.com/user-attachments/assets/bca67b84-0e5b-4d3f-a94a-aa416ae1cbb1" />
<img width="1920" height="1080" alt="Screenshot (144)" src="https://github.com/user-attachments/assets/8522ebdb-329d-4d28-ad16-304d5ac4cd0f" />
<img width="1920" height="1080" alt="Screenshot (145)" src="https://github.com/user-attachments/assets/7ee07e67-d519-4e29-a30a-7b8ffbdef1c1" />
---

### ## 💡 Real-World Impact: Potential Applications

This general-purpose SoC design is flexible enough to power a wide range of devices:
* **Wearable Technology** (e.g., fitness trackers, smartwatches)
* **Embedded Systems** (e.g., Arduino-like development boards)
* **Smart Home Devices** (e.g., controllers for appliances and sensors)
* **Consumer Electronics** (e.g., simple display controllers)

---

### ## 🏆 Week 0 Debrief: Achievements & Learnings

| Key Milestones Reached                                                               | Skills Unlocked                                                                  |
| :----------------------------------------------------------------------------------- | :------------------------------------------------------------------------------- |
| ✅ Fully operational EDA environment established.                                    | 🧠 Deepened understanding of the complete RTL-to-GDSII flow.                     |
| ✅ All core software (Yosys, iverilog, etc.) installed and verified.                   | 🧠 Gained proficiency in building tools from source code on Linux.               |
| ✅ VirtualBox and Docker container environment is stable.                            | 🧠 Improved Linux command-line and package management skills.                    |
| ✅ Project repository on GitHub initialized.                                         | 🧠 Learned the specific role of each EDA tool in the chip design ecosystem.      |

---

### ## 📓 Field Notes: Troubleshooting & Fixes

1.  **Docker Version Check:** The `docker --version` command initially failed because `docker` is aliased in the OpenLane environment.
    * **Solution:** Used `command docker --version` to bypass the alias and get the true version info.
2.  **Python Pip:** The `pip` module was not installed with the default Python 3.
    * **Solution:** Installed it manually using `sudo apt-get install python3-pip`.

---

### ## ➡️ Next Steps

```bash
# EDA Tool Version Checks
yosys --version
iverilog -V
gtkwave --version
magic --version
ngspice --version

# System Information
uname -a
lsb_release -a

# Essential Build Tools
git --version
make --version
python3 -m pip --version

#### Core Tools Status:

* **Yosys (RTL Synthesis)**
    * **Purpose:** Converts human-readable Verilog code into a machine-readable netlist of logic gates.
    * **Status:** Successfully compiled from source.
<img width="1920" height="1080" alt="Screenshot (136)" src="https://github.com/user-attachments/assets/001bc301-2ab0-4158-b37e-ad37e2ab07d1" />
* **Icarus Verilog & GTKWave (Simulation & Debugging)**
    * **Purpose:** `iverilog` compiles the Verilog code for simulation, and `gtkwave` provides a visual interface to analyze the signal waveforms and debug the design.
    * **Status:** Installed via `apt` and GUI launch confirmed.

* **Magic (VLSI Layout Viewer)**
    * **Purpose:** A powerful tool for viewing and editing the final physical layout of the chip.
    * **Status:** Pre-installed and verified.

* **OpenLane (The Automated Flow)**
    * **Purpose:** This is the master tool that automates the entire Stage O4 physical design process, from netlist to GDSII.
    * **Status:** Pre-installed and fully operational.

<img width="1920" height="1080" alt="Screenshot (137)" src="https://github.com/user-attachments/assets/ef3fcefe-2f08-442f-bf4a-6731ea4c1e40" />
<img width="1920" height="1080" alt="Screenshot (139)" src="https://github.com/user-attachments/assets/6a331522-a4d5-4009-a8dd-2c93e3f84304" />
<img width="1920" height="1080" alt="Screenshot (138)" src="https://github.com/user-attachments/assets/fd97a7df-eab5-422f-95df-d301af513c10" />
<img width="1920" height="1080" alt="Screenshot (140)" src="https://github.com/user-attachments/assets/b4b19b41-a778-44d8-917f-07f58529ce8c" />
<img width="1920" height="1080" alt="Screenshot (141)" src="https://github.com/user-attachments/assets/918f5c7e-aa9a-49c2-82f7-262531b31387" />
<img width="1920" height="1080" alt="Screenshot (142)" src="https://github.com/user-attachments/assets/bd8f82fb-9dd4-401b-9f2c-bb270d438bd2" />

<img width="1920" height="1080" alt="Screenshot (143)" src="https://github.com/user-attachments/assets/bca67b84-0e5b-4d3f-a94a-aa416ae1cbb1" />
<img width="1920" height="1080" alt="Screenshot (144)" src="https://github.com/user-attachments/assets/8522ebdb-329d-4d28-ad16-304d5ac4cd0f" />
<img width="1920" height="1080" alt="Screenshot (145)" src="https://github.com/user-attachments/assets/7ee07e67-d519-4e29-a30a-7b8ffbdef1c1" />
---

### ## 💡 Real-World Impact: Potential Applications

This general-purpose SoC design is flexible enough to power a wide range of devices:
* **Wearable Technology** (e.g., fitness trackers, smartwatches)
* **Embedded Systems** (e.g., Arduino-like development boards)
* **Smart Home Devices** (e.g., controllers for appliances and sensors)
* **Consumer Electronics** (e.g., simple display controllers)

---

### ## 🏆 Week 0 Debrief: Achievements & Learnings

| Key Milestones Reached                                                               | Skills Unlocked                                                                  |
| :----------------------------------------------------------------------------------- | :------------------------------------------------------------------------------- |
| ✅ Fully operational EDA environment established.                                    | 🧠 Deepened understanding of the complete RTL-to-GDSII flow.                     |
| ✅ All core software (Yosys, iverilog, etc.) installed and verified.                   | 🧠 Gained proficiency in building tools from source code on Linux.               |
| ✅ VirtualBox and Docker container environment is stable.                            | 🧠 Improved Linux command-line and package management skills.                    |
| ✅ Project repository on GitHub initialized.                                         | 🧠 Learned the specific role of each EDA tool in the chip design ecosystem.      |

---

### ## 📓 Field Notes: Troubleshooting & Fixes

1.  **Docker Version Check:** The `docker --version` command initially failed because `docker` is aliased in the OpenLane environment.
    * **Solution:** Used `command docker --version` to bypass the alias and get the true version info.
2.  **Python Pip:** The `pip` module was not installed with the default Python 3.
    * **Solution:** Installed it manually using `sudo apt-get install python3-pip`.

---

### ## ➡️ Next Steps

With the foundation successfully laid, the project is now ready to move into the design phase.

**Next Up: Week 1 - RTL Architecture and Design.**
