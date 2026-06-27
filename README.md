# Cable Harness Tester - 8HV 50 Signal Line

An industrial-grade, high-density hardware platform designed to test over 50 individual signal lines. This project features a robust industrial architecture optimized for field durability, scalability, and seamless manufacturing, transitioning away from standard hobbyist configurations to a reliable Eurocard standard footprint.

## 🛠️ Key Technical Specifications

*   **Form Factor:** 160mm x 100mm (Industrial Eurocard Standard) with 4x M3 mechanical corner mounting holes (4mm inset).
*   **Microcontroller:** ESP32-WROOM-32E with integrated WiFi and Bluetooth capabilities.
*   **I/O Expansion:** 4x MCP23017 I2C expanders providing a total of 64 robust logic ports.
*   **High-Voltage Monitoring:** Hardware support for 24V High-Voltage monitoring inputs.
*   **Connectors:** Pluggable 3.5mm perimeter-aligned Screw Terminals (Phoenix Contact Style) for easy harness mating.
*   **Mounting:** Full DIN-Rail compatibility for standard industrial control cabinets.

---

## ⚡ Hardware Protection & Logic Scaling

To survive rigorous industrial environments, every single signal line is heavily isolated and protected:
*   **Surge Protection:** 50x Transient Voltage Suppression (TVS) Diodes (3.3V breakdown) for high-voltage surge clamping.
*   **Current Limiting:** 50x 330Ω resistors arranged in a high-density logic channel protection matrix.
*   **ADC Voltage Scaling:** Dedicated resistor voltage divider networks ($90.9\text{ k}\Omega + 10\text{ k}\Omega$) safely step down 24V external signals to $2.9\text{V}$ MCU-safe logic levels.

---

## 📐 Professional Layout & "Waterfall" Architecture

The PCB utilizes a structured **Waterfall Architecture** to guarantee signal integrity, RF performance, and clean field-wire management:

1. **Perimeter Alignment:** All main terminal blocks are fixed to the extreme top ($Y = 3.5\text{mm}$) and bottom ($Y = 96.5\text{mm}$) bounds of the board, offering massive clearance for heavy external wire plugs.
2. **Linear Component Pipeline:** Signals route logically in vertical columns, flowing straight from the central MCP expansion chips through the series resistors and TVS diodes directly to the terminal connectors.
3. **RF Optimization:** The ESP32 MCU is positioned on the far edge of the PCB with its antenna facing completely outward, preserving a cleared keep-out zone and ensuring zero interference from the high-voltage 24V planes.

---

## 🗂️ Component Identification Guide

### 🧱 3D PCB Layout
*   **Microcontroller Unit (U1):** Positioned on the edge zone to guarantee absolute WiFi antenna clearance.
*   **I/O Expansion Cluster (U2-U5):** Center-aligned array of 4x MCP23017 ICs processing the 50+ lines of logic.
*   **Protection Matrix:** High-density grid of SMD 330Ω resistors and TVS diodes occupying the right-hand logic channels.
*   **Industrial Interface:** Pluggable screw terminal blocks lining the top/bottom perimeters.
*   **Power & Control Zone:** Top right quadrant containing the 24V power input terminal, status indicators, and physical boot/reset tactile buttons.

### 🔌 Schematic Layout
*   **Protection Channel:** Repeated R-D (Resistor-Diode) pairs preventing high voltage feedback.
*   **I2C Control Bus:** Shared SDA/SCL lines multiplexing the expansion cluster directly back to the ESP32.
*   **24V ADC Scaling:** Precision voltage dividers matching the physical high voltage input values to system logic thresholds.

---

## 📈 Status
*   **Board Dimensions & Mechanical Insets:** Complete
*   **50-line TVS/Resistor Safety Protection:** Complete
*   **ESP32 RF Edge Placement Constraints:** Complete
*   **Pluggable Industrial Terminal Layout:** Complete
*   **BOM & Pick-and-Place Target Export:** Ready for Production
