# IoT Challenge #1: Smart Home Motion Sensor
**Course:** Internet of Things (IoT)  
**Institution:** Politecnico di Milano  
**Professor:** Cesana Matteo

## 1. Project Description
This project implements a commercial-style IoT motion sensor node designed for a smart home environment. The node detects human motion and measures ambient light levels (illuminance). This data is transmitted to a central **SINK node**, which then decides if room lights should be toggled.

## 2. Technical Specifications
* **Microcontroller:** ESP32.
* **Communication Protocol:** ESP-NOW.
* **Target Address:** Broadcast address `FF:FF:FF:FF:FF:FF`.
* **Data Format:** Single string transmission.
  * `MOTION_DETECTED-LUMINOSITY:ZZZ`
  * `MOTION_NOT_DETECTED-LUMINOSITY:ZZZ`

## 3. Power Management (Duty Cycle)
To optimize energy consumption, the node utilizes a duty cycle involving **Deep Sleep**.
* **Leader Person Code:** 10692911
* **Deep Sleep Duration (X):** **1.6 seconds** (Calculated as (11 % 50 + 5) / 10).
* **Battery Energy (Y):** **17911 Joules** (Calculated as 2911 % 5000 + 15000).

The node wakes up, senses the environment, transmits the data, and immediately returns to Deep Sleep.

## 4. Energy Estimation Analysis
The project includes a detailed estimation of power consumption for each state:
* **Deep Sleep State**
* **Transmission State** (ESP-NOW at different dBm levels)
* **Sensor Reading Phase**
* **Idle State**

Measurements of state durations were performed in the Wokwi emulator using `micros()` to ensure high-fidelity energy modeling.

## 5. Team Members
* **Sajad Ghadiri** 
* **Fatemeh Kiani** 

## 6. Project Structure
* `Challenge1.ino`: ESP32 source code.
* `diagram.json`: Wokwi hardware connection diagram.
* `Challenge.pdf`: Final report containing code logic, energy plots, and proposed improvements.
