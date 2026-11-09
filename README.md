# Arduino MAX30102 Heart Rate Monitor with OLED & Buzzer

An Arduino-based real-time heart rate (BPM) monitoring project using the **MAX30102** pulse oximeter & heart-rate sensor, an **I2C OLED Display (128x32)**, and a **buzzer**.

Whenever a heartbeat is detected, the OLED displays a beating heart animation alongside the calculated average BPM, and the buzzer emits a short synchronous beep.

---

## 📸 Overview & Features

- **Finger Detection:** Checks infrared (IR) sensor values to detect when a finger is placed on the sensor.
- **Heartbeat Animation:** Displays dynamic heart bitmap icons on the 128x32 OLED screen.
- **Average BPM Calculation:** Samples and averages the last 4 valid beats to filter noise and provide stable readings.
- **Auditory Feedback:** Sounds a piezo buzzer synchronously with detected heartbeats.

---

## 🧰 Hardware Requirements

| Component | Description | Quantity |
| :--- | :--- | :--- |
| **Arduino Uno / Nano** | Microcontroller board | 1 |
| **MAX30102** | Pulse Oximeter & Heart Rate Sensor Module | 1 |
| **OLED Display** | 0.91" 128x32 I2C OLED (SSD1306) | 1 |
| **Piezo Buzzer** | Passive / Active 5V Buzzer | 1 |
| **Breadboard & Jumpers** | For circuit connections | 1 set |

---

## 🔌 Circuit Wiring & Pinout

Both the **MAX30102** sensor and the **OLED display** communicate over the **I2C** protocol and share the Arduino's I2C bus pins (`A4` and `A5` on Arduino Uno/Nano).

### Pin Connection Table

| Device | Device Pin | Arduino Uno / Nano Pin |
| :--- | :--- | :--- |
| **MAX30102** | `VIN` / `VCC` | `5V` (or `3.3V` depending on module) |
| | `GND` | `GND` |
| | `SDA` | `A4` (I2C Data) |
| | `SCL` | `A5` (I2C Clock) |
| **128x32 OLED** | `VCC` | `5V` (or `3.3V`) |
| | `GND` | `GND` |
| | `SDA` | `A4` (I2C Data) |
| | `SCL` | `A5` (I2C Clock) |
| **Buzzer** | `+` (Positive) | `Digital Pin 3` |
| | `-` (GND) | `GND` |

---

## 📚 Required Arduino Libraries

Before uploading the sketch, make sure to install the following libraries via the **Arduino IDE Library Manager** (`Sketch` -> `Include Library` -> `Manage Libraries...`):

1. **SparkFun MAX3010x Pulse and Proximity Sensor Library** (by *SparkFun Electronics*)
   - Provides `MAX30105.h` and `heartRate.h`
2. **Adafruit SSD1306** (by *Adafruit*)
3. **Adafruit GFX Library** (by *Adafruit*)

---

## 🚀 How to Run

1. Connect the circuit according to the wiring table above.
2. Open [`arduino-max30102-heart-rate-monitor.ino`](arduino-max30102-heart-rate-monitor.ino) in the Arduino IDE.
3. Select your board (`Tools` -> `Board` -> `Arduino Uno`) and the appropriate COM Port.
4. Click **Upload**.
5. Once uploaded, place your index finger gently on the MAX30102 sensor. Avoid pressing too hard to ensure accurate blood flow detection.

---

## 🙏 Credits & Attribution

This project is based on the tutorial and implementation by **[SurtrTech](https://www.surtrtech.com)**:
- Project Reference: [Measure Heart Rate and SpO2 with MAX30102](https://www.hackster.io/SurtrTech/measure-heart-rate-and-spo2-with-max30102-c94483)
- YouTube Channel: [SurtrTech](https://www.youtube.com/c/SurtrTech)
- Original heart rate algorithm provided by the SparkFun MAX3010x Library.

---

## 📄 License

This repository is provided for educational and maker purposes under the [MIT License](LICENSE).
