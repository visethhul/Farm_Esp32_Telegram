# Farm_Esp32_Telegram
I am working on an ESP32 project with the following setup:

- ESP32 with WiFi
- Telegram Bot for remote control
- SSD1306 OLED display (I2C, SDA=21, SCL=22)
- DHT sensor for temperature/humidity
- Ultrasonic sensors for tank/fertilizer level
- Relay module for controlling fertilizer pump

Main features:
1. Show dynamic status on OLED
    1.1. Status 1 (Internet :Connected or Disconnected \n Date : 01/10/2025 \n Time: 8:09 PM )
    1.2.Status 2 (Tank W: XX%,\n Pump : Activ or Stop \n,Temp: XXC, \n
    1.3. Status 3 (Tank F: XX%, Schedule: Active or disactive, Relay F: 10 Sec on 0r off \n ,Meter Water: xxxxL/Date ).
    noted : all of three Status show 20 sec loop
3. Control via Telegram bot commands (/status, /fertilizer_on_xx, etc.).
     3.1 commands /status how infomation  below 
      Tank W: XX%,\n
      Pump : Activ or Stop \n
      Temp: XXC, \n
      Tank F: XX%
      Schedule: Active or disactive,
      Relay F: 10 Sec on 0r off  
      Meter Water: xxxxL/Day (reset everyday )
      3.2 /fertilizer_on_xxxsec when set this command message replay from system : fertilizer Wating to see Tank W Full 
      when condition tank water full and fertilizer set on push message to telegram Relay F: xxx Sec On  
5. When fertilizer is scheduled, show the real date & time of end schedule (not static text).
6. WiFi + NTP used to keep real-time clock.

👉 Please help me:
- Fix or improve my code.
- Make the OLED and Telegram messages dynamic.
- Provide easy-to-copy code snippets.

Here is the code I currently use:
[ paste your code here ]
