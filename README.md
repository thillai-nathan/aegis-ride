# 🛡️ AEGIS RIDE

### Smart Vehicle Safety & Road Condition Telemetry System

**An ESP32-based IoT project for road-event monitoring, crash detection, rider alerts, and emergency SOS communication.**

## 👥 Project Authors

* **Thillai Nathan**
* **Fathima Asrah**

## 📌 About the Project

AEGIS RIDE is an IoT-based vehicle safety prototype designed to monitor vehicle motion, identify potential road hazards, and assist riders during emergency situations.

The system uses an ESP32 microcontroller to process sensor readings, display information on an OLED screen, and provide a web-based dashboard for monitoring vehicle telemetry. When an emergency is triggered, the system can attempt to send an SOS alert through Telegram when an internet connection is available.

## 🎯 Objectives

* Detect and classify road impacts using motion-sensor data.
* Identify speed breakers and significant vehicle tilting.
* Monitor vehicle movement and available battery information.
* Obtain rider coordinates using a GPS module or supported phone-location integration.
* Provide a manual SOS trigger and countdown cancellation.
* Display live telemetry and recent events on a mobile-friendly dashboard.
* Send emergency notifications through Telegram when connectivity permits.

## 🧰 Hardware Components

| Component               | Purpose                                   |
| ----------------------- | ----------------------------------------- |
| ESP32 Dev Module        | Main controller and Wi-Fi connectivity    |
| MPU6050                 | Acceleration and orientation measurements |
| NEO-6M GPS              | Outdoor positioning and speed data        |
| SSD1306 OLED            | Local status and event display            |
| Buzzer                  | Audible warnings                          |
| Push button             | Manual control and SOS interaction        |
| Battery voltage divider | Battery-voltage measurement               |

## 💻 Software and Technologies

* Arduino IDE
* ESP32 Arduino framework
* Embedded C++
* HTML, CSS and JavaScript
* HTTP web server
* Wi-Fi access point and station modes
* Telegram Bot API
* Google Maps location links

## ⚙️ System Workflow

1. The ESP32 initializes the sensors and display.
2. The MPU6050 supplies acceleration and orientation measurements.
3. The firmware processes the readings to identify possible road events.
4. Telemetry and event information are displayed on the OLED and web dashboard.
5. A detected emergency or manual SOS action initiates the configured alert process.
6. The firmware attempts Telegram delivery when internet access is available.
7. The rider can cancel an eligible countdown or dismiss the displayed SOS status.

## 🌐 Web Dashboard

The dashboard implemented in the firmware provides:

* Live sensor telemetry
* Emergency SOS and cancellation controls
* Battery information
* GPS and location information
* Google Maps link
* Recent event history
* Last-event display

**Local access:** Connect to the ESP32 access point and open `http://192.168.4.1` in a browser.

Remote Telegram delivery requires a separate working internet connection for the ESP32. Local dashboard access alone does not guarantee that an emergency message will reach another person.

## 🔌 Pin Connections

| Module          | ESP32 connection                           |
| --------------- | ------------------------------------------ |
| MPU6050 SDA     | GPIO 21                                    |
| MPU6050 SCL     | GPIO 22                                    |
| OLED SDA        | GPIO 21                                    |
| OLED SCL        | GPIO 22                                    |
| GPS TX          | GPIO 16 (ESP32 RX2)                        |
| GPS RX          | GPIO 17 (ESP32 TX2)                        |
| Buzzer positive | GPIO 25                                    |
| Push button     | GPIO 4 and GND                             |
| Battery sensing | GPIO 34 through a suitable voltage divider |

## 🚀 Setup Instructions

1. Install the Arduino IDE and ESP32 board support.
2. Open the project firmware in the Arduino IDE.
3. Verify the wiring and sensor connections.
4. Configure Wi-Fi and Telegram credentials privately; do not commit secrets to GitHub.
5. Select the correct ESP32 board and serial port.
6. Upload the firmware.
7. Open Serial Monitor at 115200 baud.
8. Connect your phone to the configured ESP32 access point.
9. Open `http://192.168.4.1` to access the dashboard.
10. Test each feature individually before performing integrated tests.

## 🧪 Testing and Validation

Record the actual results of these tests:

* MPU6050 initialization and changing sensor readings
* GPS fix and coordinate validation
* OLED status updates
* Road-event classification
* Manual SOS activation
* Countdown cancellation
* Telegram delivery with internet access
* Dashboard operation during sensor activity
* Battery-voltage measurement

Do not report detection accuracy or successful emergency delivery until the corresponding tests have been completed.

## 🔐 Security Considerations

* Keep Wi-Fi passwords and Telegram tokens out of public source code.
* Use certificate verification for HTTPS requests.
* Validate dashboard commands and incoming data.
* Test the system in a controlled environment.
* Do not rely on this academic prototype as the sole means of emergency protection.

## 🔮 Future Enhancements

* Improve crash-detection reliability through repeated testing.
* Add persistent event history and downloadable reports.
* Develop a companion mobile application.
* Improve GPS diagnostics and location freshness indicators.
* Add sensor-health monitoring and low-battery warnings.
* Improve dashboard accessibility and responsive design.
* Evaluate detection performance using recorded test data.

## ⚠️ Disclaimer

AEGIS RIDE is an academic prototype. Its alerts, sensor readings, location estimates, and network delivery depend on hardware performance and connectivity. It is not a certified vehicle safety or emergency-response system.
