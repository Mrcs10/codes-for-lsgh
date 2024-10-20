---

 Vehicle-to-Grid (V2G) System Using PWM Control

This repository contains Arduino code for controlling the bidirectional power flow between a battery and the electrical grid using Pulse Width Modulation (PWM). These codes regulate the charging and discharging of a battery based on battery voltage, grid demand, and the battery's State of Charge (SOC). The objective is to maintain battery health and ensure efficient energy transfer between a battery and the grid, simulating a V2G environment.

 Table of Contents
- [Overview](#overview)
- [Code Descriptions](#code-descriptions)
- [Setup Instructions](#setup-instructions)
- [Hardware Requirements](#hardware-requirements)
- [How it Works](#how-it-works)
- [Example Use Cases](#example-use-cases)

---

Overview

Vehicle-to-Grid (V2G) technology enables electric vehicles (EVs) to store energy and return it to the grid during peak demand times. This system makes use of PWM signals to manage charging and discharging dynamically, based on conditions such as the battery's voltage, grid demand, and SOC. These codes simulate the process using a battery pack instead of a vehicle.

 Code Descriptions

1. **Bidirectional PWM Control for Charging and Discharging**
   - **Purpose**: Monitors battery voltage and adjusts the PWM signal to charge or discharge the battery.
   - **Functionality**: 
     - If the battery voltage is low, the system charges the battery.
     - If the voltage is high, it discharges energy to the grid.
     - Serial output for voltage, current, and duty cycle values.
   
2. **PWM-Based Battery Protection and Grid Support**
   - **Purpose**: Adds grid demand as a key factor in determining charging/discharging.
   - **Functionality**: 
     - When grid demand is high and battery is charged, discharges energy into the grid.
     - When grid demand is low and battery is not fully charged, it charges the battery.

3. **Bidirectional PWM with Battery SOC Feedback**
   - **Purpose**: Uses the battery’s State of Charge (SOC) to control energy flow.
   - **Functionality**: 
     - The SOC is calculated from voltage.
     - If SOC is below 50%, the battery charges; if SOC is above 90%, it discharges.

 4. **Adaptive PWM for Grid Fluctuation and Battery Protection**
   - **Purpose**: Handles both battery voltage and grid fluctuations using PWM control.
   - **Functionality**: 
     - When grid demand fluctuates or voltage exceeds thresholds, adjusts PWM signal for charging/discharging.
     - When no significant action is required, the system enters idle mode to save energy.

---

 Setup Instructions

1. **Install Arduino IDE**: Download and install the Arduino IDE on your computer from the official website: [https://www.arduino.cc/en/software](https://www.arduino.cc/en/software).

2. **Connect the Arduino**: 
    - Connect your Arduino board to your computer via USB.
    - Ensure that you have the required hardware components like voltage sensors, MOSFETs, and a battery pack.

3. **Upload the Code**:
    - Choose one of the `.ino` files from the repository.
    - Open the file in the Arduino IDE.
    - Select the correct board and port from **Tools > Board** and **Tools > Port**.
    - Click the upload button to send the code to your Arduino.

---

Hardware Requirements

- **Arduino Board** (e.g., Arduino Uno)
- **Battery Pack** (can be simulated with a Li-Ion battery)
- **Voltage Divider** (for voltage sensing)
- **PWM Compatible Driver Circuit** (e.g., MOSFETs for bidirectional control)
- **Grid Simulation** (a light bulb or resistive load to represent grid load)
- **Resistors** and **capacitors** for filtering

---

How it Works

1. **PWM Signal Generation**: The Arduino generates a PWM signal based on real-time measurements of battery voltage, SOC, and grid demand. This signal controls the amount of power delivered to or taken from the battery.
   
2. **Bidirectional Power Flow**: The system decides whether to charge or discharge the battery. When the battery voltage is below the threshold or grid demand is low, the system charges the battery. When the battery voltage is high or grid demand spikes, it discharges energy into the grid.

3. **Monitoring**: The system continuously outputs important data such as battery voltage, SOC, and duty cycle for the PWM signal via Serial communication. This allows real-time monitoring of the system’s performance.

---

 Example Use Cases

1. **Vehicle-to-Grid Systems**: The PWM codes can be adapted for a V2G application where electric vehicle batteries are used to store energy during low-demand periods and supply energy to the grid during peak demand times.

2. **Battery Management Systems**: The codes can be used in battery management systems to ensure batteries are maintained at optimal voltage levels and their health is preserved by avoiding overcharging or over-discharging.

3. **Renewable Energy Storage**: This code can help store excess energy produced by solar panels or wind turbines in battery systems and feed energy back to the grid when needed.

---

 Contact
For issues or contributions, feel free to raise a pull request or open an issue.

---

