# Farm_Esp32_Telegram
I am working on an ESP32 project with the following setup:

- ESP32 with WiFi
- Telegram Bot for remote control
- SSD1306 OLED display (I2C, SDA=21, SCL=22)
- DHT sensor for temperature/humidity
- Ultrasonic sensors for tank/fertilizer level
- Relay module for controlling fertilizer pump

Main features:
1. Show dynamic status on OLED (Tank %, Temp, Fertilizer %, Schedule info).
2. Control via Telegram bot commands (/status, /fertilizer_on_xx, etc.).
3. When fertilizer is scheduled, show the real date & time of end schedule (not static text).
4. WiFi + NTP used to keep real-time clock.

👉 Please help me:
- Fix or improve my code.
- Make the OLED and Telegram messages dynamic.
- Provide easy-to-copy code snippets.

Here is the code I currently use:
[ paste your code here ]
