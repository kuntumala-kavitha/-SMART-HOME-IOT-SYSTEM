# Smart Home IoT System using Raspberry Pi

 Overview
This project implements a **Smart Home IoT System** using a **Raspberry Pi**. It integrates various sensors and actuators to create a smart home environment that can be remotely monitored and controlled via a web interface or MQTT. The system collects data from temperature, humidity, and motion sensors and controls home appliances like lights through a relay.

## Features
- **Real-time monitoring** of environmental data such as temperature, humidity, and motion detection.
- **Remote control** of appliances (e.g., lights) using a web interface and MQTT protocol.
- **Web-based dashboard** for easy access and control of smart home devices.
- **MQTT integration** for controlling devices from any MQTT client.
- Supports future expansion with additional sensors (smoke detector, cameras, etc.).

## Components Used
 Hardware
- **Raspberry Pi** (any model with GPIO support, like Raspberry Pi 3/4)
- **DHT11/DHT22 sensor** (Temperature and Humidity Sensor)
- **PIR Motion Sensor**
- **Relay Module** (to control appliances)
- **LED** (as a demo for lighting control)
- **Breadboard and Jumper Wires**
 Software
- **Python**
- **Flask** (for web interface)
- **paho-mqtt** (for MQTT communication)
- **Adafruit_DHT Library** (for DHT sensor)
- **RPi.GPIO Library** (for GPIO control)

## Installation

 1. Raspberry Pi Setup
Ensure that your Raspberry Pi is set up with Raspbian OS. Make sure it has internet access and that the necessary libraries are installed.


sudo apt-get update
sudo apt-get upgrade


 2. Install Required Python Libraries
Install the required libraries for sensor data acquisition, GPIO control, and web server functionality.


sudo pip install Adafruit_DHT RPi.GPIO Flask paho-mqtt

 3. Hardware Connections
 **DHT11/DHT22**: Connect Pin 1 to 3.3V, Pin 2 to GPIO 4, and Pin 4 to GND.
**PIR Sensor**: Connect VCC to 5V, GND to GND, and OUT to GPIO 17.
**Relay Module**: Connect VCC to 5V, IN1 to GPIO 18, and GND to GND.
 **LED**: Connect to the relay output to simulate lighting control.

 4. Clone the Repository
Clone the repository to your Raspberry Pi:
git clone https://github.com/your-username/smart-home-iot.git
cd smart-home-iot


 5. Running the Project
Run the Python scripts to start the web server and enable MQTT functionality.


python3 app.py


Access the web interface at:
http://<your-raspberry-pi-ip>:5000/status

 6. Using MQTT
You can control the system using MQTT. Publish messages (e.g., "on" or "off") to control appliances.

Example using Mosquitto:
mosquitto_pub -h broker.hivemq.com -t "smarthome/control" -m "on
 Project Structure

 app.py               # Flask web server to control and monitor devices
 sensors.py           # Handles reading from DHT11 sensor and PIR sensor
 mqtt_client.py       # MQTT client for communication
 templates/
 index.html       # Web interface


 How It Works
- The **DHT11 sensor** measures the room's temperature and humidity, providing real-time data.
- The **PIR sensor** detects motion, which can be used for security or automated lighting.
- A **Relay Module** controls the LED (simulating a home appliance) through GPIO pins.
- The **Flask web server** provides a user interface for remote monitoring and control.
- **MQTT** enables remote control of devices from any MQTT client by publishing messages to subscribed topics.

 Future Enhancements
- Add more sensors such as smoke detectors, water level sensors, or cameras.
- Implement home security features like door locks and window monitoring.
- Expand MQTT capabilities for a full-fledged smart home ecosystem.
- Integrate voice assistants like Google Assistant or Alexa.


