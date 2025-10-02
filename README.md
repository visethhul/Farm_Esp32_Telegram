# Farm_Esp32_Telegram
Great question 👍 Since the ESP32 has many GPIOs but some are better suited for certain peripherals, I’ll recommend **safe and reliable pin mappings** for your project. These pins avoid conflicts with boot, flash, and strapping pins.

---

## ✅ Recommended Pin Assignments (ESP32 DevKit V1)

* **OLED SSD1306 (I2C):**

  * SDA → **GPIO 21**
  * SCL → **GPIO 22**
    *(default and stable for ESP32 I²C)*

* **DHT22 sensor (Temp/Humidity):**

  * Data → **GPIO 4**

* **Ultrasonic Sensors:**

  * Tank Water → TRIG=**GPIO 5**, ECHO=**GPIO 18**
  * Fertilizer Tank → TRIG=**GPIO 19**, ECHO=**GPIO 23**

* **Relay Module (Fertilizer Pump):**

  * Relay control → **GPIO 25**
    *(good as digital output, won’t conflict with boot)*

* **XKC Sensor (Pump/Tank status detection):**

  * Signal → **GPIO 26**
    *(ADC capable if analog, or digital input if simple ON/OFF)*

* **YF Water Flow Sensor:**

  * Signal → **GPIO 27**
    *(supports hardware interrupts for pulse counting)*

---

## ⚡ Pin Map Summary

| Component             | Pin(s) Used      |
| --------------------- | ---------------- |
| OLED (I2C)            | SDA=21, SCL=22   |
| DHT22                 | 4                |
| Tank Water Ultrasonic | TRIG=5, ECHO=18  |
| Fertilizer Ultrasonic | TRIG=19, ECHO=23 |
| Relay Fertilizer Pump | 25               |
| XKC Sensor            | 26               |
| YF Water Flow Sensor  | 27               |

---

Got it ✅. Right now your request is a bit mixed (hardware notes + feature list + code issues).
Let me **rewrite your prompt clearly** so it’s easy for me (or anyone else) to generate correct ESP32 code for you.

---

## ✍️ Rewritten Prompt

I am building a project called **Farm_Esp32_Telegram** with the following hardware:

* **ESP32** with WiFi
* **Telegram Bot** for remote control
* **SSD1306 OLED display** (I2C, SDA=21, SCL=22)
* **DHT22 sensor** for temperature/humidity (connected to pin XX)
* **Ultrasonic sensors**:

  * Tank water level (TRIG=XX, ECHO=XX)
  * Fertilizer tank level (TRIG=XX, ECHO=XX)
* **Relay module** to control fertilizer pump (pin XX)
* **XKC sensor** to detect if pump/tank is working (pin XX)
* **YF water flow sensor** (pin XX) → measure daily water usage, reset every midnight

---

### 🔹 Features Required

1. **Dynamic OLED Status (4 screens, rotate every 20 sec):**

   * **Status 1:**

     * Internet: Connected/Disconnected
     * Date: DD/MM/YYYY
     * Time: HH:MM AM/PM
   * **Status 2:**

     * Tank Water: XX%
     * Pump TW: T or F
     * Temperature: XX°C
   * **Status 3:**

     * Tank Fertilizer: XX%
     * Schedule: T or F
     * Relay Fertilizer: XX sec ON / OFF
     * Water Meter: XXXX L/day (reset daily)
   * **Status 4:**

     * Pump Fertilizer: T or F

---

2. **Telegram Bot Commands:**

   * `/status` → reply with:

     ```
     Tank W: XX%
     Pump TW: T or F
     Temp: XX°C
     Tank Fer: XX%
     Schedule Fer: T or F
     Relay F: XX sec ON or OFF
     Meter Water: XXXX L/day
     Pump Fer: T or F
     ```

   * `/fertilizer_on_xxxsec` →

     * System replies: `Fertilizer waiting until Tank Water > 80%`
     * When Tank Water > 80% → relay fertilizer turns ON → system sends Telegram message:

       ```
       Relay Fer: ON
       Schedule Fer: T
       End Time: YYYY-MM-DD HH:MM:SS
       ```

   * `/fertilizer_off` → immediately turn OFF fertilizer relay → push Telegram message:

     ```
     Relay Fer: OFF
     Schedule Fer: F
     ```

---

3. **Real-Time Clock (RTC/NTP):**

   * WiFi + NTP for automatic date & time sync.
   * Fertilizer schedule should show **real end time** instead of static text.

---

👉 Please help me:

* Write **clean, easy-to-copy ESP32 code** for this project.
* Ensure OLED and Telegram messages update dynamically.
* Include **water flow meter daily reset** at midnight.
* Make the fertilizer relay scheduling system work as described.

---

⚡ Question for you: do you want me to **fill in pin numbers** (I can assign recommended defaults) or should I leave them as placeholders (XX) so you can map them yourself?

---

