# 🛰️ LoRa Satellite Ground Station Tracking System

![Status](https://img.shields.io/badge/Status-Live_%26_Operational-success?style=flat-square)
![Hardware](https://img.shields.io/badge/Hardware-ESP32%20%7C%20Dual_RA--02-1f618d?style=flat-square)
![Network](https://img.shields.io/badge/Network-TinyGS%20%7C%20MQTT-d35400?style=flat-square)
![Modulation](https://img.shields.io/badge/Modulation-Chirp_Spread_Spectrum_(CSS)-6c3483?style=flat-square)

> **A low-cost, automated LPWAN ground station engineered to receive, decode, and log real-time telemetry from Low Earth Orbit (LEO) CubeSats.**[cite: 23, 24]

---

## 🔴 LIVE SATELLITE TRACKING DASHBOARD
**The ground station is currently active and autonomously tracking satellite passes.** 
📡 **[View Live Telemetry Data on TinyGS](https://app.tinygs.com/station/GNDEC@wDgUnkdh6fW6PtWr)**

*(Click the link above to view real-time packets, signal quality, and satellite tracking history received by this specific hardware node).*

---

## 📖 Project Overview
This project focuses on the hardware design and RF (Radio Frequency) optimization of a dedicated LoRa-based satellite ground station. Integrated with the global open-source **TinyGS network**, the system automatically tunes to incoming satellite transmission frequencies (e.g., 433MHz / 868MHz ISM bands) to receive critical health payloads[cite: 23, 24].

**Tracked Telemetry Parameters:**
*   Battery Voltage & Temperature[cite: 23]
*   Solar Panel Voltage[cite: 23]
*   CPU Status & Payload Health[cite: 23]

---

## ⚙️ System Architecture & Hardware Specs
To ensure high-reliability reception over long distances (several kilometers through the atmosphere), the ground station integrates precise power regulation and RF routing[cite: 23].

**Core Subsystems:**
*   **Microcontroller:** ESP32 (Handles TinyGS firmware, frequency auto-tuning, and MQTT server communication)[cite: 20, 23].
*   **RF Transceiver:** AI-Thinker RA-02 (SX1278) LoRa module utilizing CSS modulation for high noise/interference resistance[cite: 23, 24].
*   **Power Regulation:** Dedicated **Buck (Step-Down) Converter** to stabilize voltage for the sensitive RF modules, preventing signal dropouts during high-current ESP32 Wi-Fi transmissions[cite: 23].
*   **RF Connectivity:** U.FL to SMA patch cords minimizing insertion loss[cite: 23].
*   **User Interface:** 0.95” OLED Display for on-site, real-time telemetry readout and system debugging[cite: 23].

### 🔌 Circuit Design
![Circuit Schematic](./docs/IMG-20260504-WA0014.jpg)
*(ESP32 interfaced with RA-02 transceiver, Buck Converter, and OLED Display)*

---

## 📡 Network & Data Flow
1. **Reception:** The custom-tuned antenna receives LoRa packets from passing LEO CubeSats[cite: 23].
2. **Decoding:** The ESP32 decodes the CSS modulated signal locally.
3. **Transmission:** Data is pushed via REST API / MQTT Server to the TinyGS cloud and integrated Telegram bots[cite: 20].
4. **Logging:** Packet success/failure rates, signal-to-noise ratio (SNR), and historical telemetry are logged on the live dashboard for long-term satellite lifecycle monitoring[cite: 23].

---

## 🏆 Project Credentials
*   **Institution:** Guru Nanak Dev Engineering College (GNDEC), Ludhiana[cite: 23, 24]
*   **Developers:** Gurnoor Kaur & Gurpuneet Singh Hunjan[cite: 23, 24]
*   **Documentation:** 
    *   [Read the Full Project Synopsis](./docs/Satellite report file ok.pdf)[cite: 24]
    *   [View the Presentation Deck](./docs/GROUND_STATION_FOR_TRACKING_LoRa_SATELLITES.pptx)[cite: 22]
