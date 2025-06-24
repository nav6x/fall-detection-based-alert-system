# Fall Detection Based Alert System (FDBAS)

A smart IoT system that detects falls using an MPU6050 sensor and sends alerts via IFTTT.

## Hardware Requirements

* NodeMCU ESP8266
* MPU6050 (Accelerometer and Gyroscope sensor)
* Jumper wires
* USB cable for programming

## Pin Connections

MPU6050 to NodeMCU:
* VCC -> 3.3V
* GND -> GND
* SCL -> D1
* SDA -> D2

## Software Requirements

* Arduino IDE
* Required Libraries:
  - Wire.h
  - ESP8266WiFi.h

## Setup Instructions

1. Connect the hardware according to the pin connections above
2. Install Arduino IDE and required libraries
3. Update the following variables in the code:
   ```cpp
   const char *ssid = "your_wifi_ssid";
   const char *pass = "your_wifi_password";
   const char *privateKey = "your_ifttt_key";
   ```
4. Upload the code to NodeMCU

## How It Works

The system uses a three-stage fall detection algorithm:
1. Detects free fall (low acceleration)
2. Detects impact (high acceleration)
3. Confirms orientation change

When a fall is detected, an alert is sent through IFTTT to notify caregivers.

## Calibration

The system uses calibration values for the MPU6050:
* Accelerometer: AcX-2050, AcY-77, AcZ-1947
* Gyroscope: GyX+270, GyY-351, GyZ+136

You may need to adjust these values based on your sensor.

## Troubleshooting

* Ensure proper WiFi credentials
* Check IFTTT webhook key
* Verify I2C connections
* Monitor Serial output for debugging

## License

Open source - Feel free to modify and distribute with attribution.
