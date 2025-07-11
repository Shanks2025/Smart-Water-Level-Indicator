# Smart-Water-Level-Indicator


This project is designed to reduce water wastage from over-head tanks . We used ultrasonic sensor to measure water level,a LCD screen to display water level in % and integrated with Blynk App to monitor the water level reamining.
This could also be made more effective by integrating to motor to switch on and off automatically.
---

##  Components Used

- ESP8266 NodeMCU
- Ultrasonic Sensor
- 5V Relay Module
- 16x2 LCD (Standard)
- Water Pump (DC Motor)
- Breadboard and Jumper Wires
- External 5V Power Supply (for pump and relay)

---

## How It Works

- The ultrasonic sensor continuously measures the distance between the top of the tank and the water surface.
- This distance is converted into a percentage to represent the tank’s fill level.
- The water level is displayed on a 16x2 LCD in percentage format and in the Blynk App
- Additionally, packet-level communication was analyzed using Wireshark to validate network behavior and cloud interactions.

---

## Circuit Connections

### Ultrasonic Sensor :
- VCC → 3.3V (ESP8266)
- GND → GND
- TRIG → D5 (GPIO14)
- ECHO → D6 (GPIO12)

### Relay Module:
- IN → D7 (GPIO13)
- VCC → 5V (external)
- GND → GND

### LCD (16x2 Standard):
- RS → D1
- EN → D2
- D4 → D3
- D5 → D4
- D6 → D8
- D7 → D0
- VCC, GND → 5V, GND

---

##  Packet Analysis with Wireshark

Wireshark was used to inspect packets exchanged between the ESP8266 and the cloud (e.g., Blynk or custom server). It confirmed:
- Reliable TCP connections
- Proper MQTT communication (if used)
- Network connectivity test using Ping on Terminal
- Capturing Packets based on Filters

Screenshots of the captured packets are included in the `images/` folder.

---

##  How to Run

1. Upload the `SmartWaterLevel.ino` sketch to your ESP8266. Download necessary Modules if required within ArduinoIDE.
2. Make the hardware connections as shown in the diagram.
3. Power the ESP8266 via USB and the relay+motor via external 5V supply and make sure that the WiFi used by Blynk app and WiFi name and password written within code are same.
4. Monitor the water level on the LCD.
5. Check notifications or packet logs (if networked).

---


