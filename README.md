# IoT Parrot Health Monitoring System 🦜

**Smart Environmental Monitoring System with ESP8266, Sensors, and Mobile App**

<div align="center">

![IoT](https://img.shields.io/badge/IoT-00979D?style=for-the-badge&logo=arduino&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-00979D?style=for-the-badge&logo=arduino&logoColor=white)
![ESP8266](https://img.shields.io/badge/ESP8266-E7352C?style=for-the-badge&logo=espressif&logoColor=white)

</div>

---

## 📋 Overview

An innovative **Internet of Things (IoT)** project that monitors environmental conditions critical to parrot health. This system integrates multiple sensors with ESP8266 microcontroller, Python backend server, and a Kivy-based mobile application to provide **real-time health monitoring** for pet parrots.

The project demonstrates practical hardware-software integration for animal welfare applications, combining embedded systems, sensor networks, mobile development, and data visualization.

---

## 🎯 Problem Statement

Parrots are sensitive to environmental conditions including temperature, humidity, air quality, sound levels, and lighting. Suboptimal conditions can lead to health issues, stress, and behavioral problems. Manual monitoring is time-consuming and impractical for continuous care.

**Challenge:**  
Create an automated, real-time monitoring system that tracks multiple environmental parameters, alerts caretakers to dangerous conditions, and provides historical data for health analysis.

---

## 🚀 Objectives

1. **Real-time Monitoring**: Continuous sensor data collection from parrot environment
2. **Multi-parameter Tracking**: Temperature, humidity, air quality, sound, and light levels
3. **Mobile Accessibility**: User-friendly mobile app for remote monitoring
4. **Data Visualization**: Historical trends and real-time dashboards
5. **Alert System**: Notifications for abnormal environmental conditions
6. **Hardware Integration**: Seamless ESP8266 microcontroller and sensor connectivity

---

## ✨ Features

### Hardware Features
- ✅ **Multi-sensor integration** (5 environmental sensors)
- ✅ **ESP8266 microcontroller** for WiFi connectivity
- ✅ **Low-power operation** for continuous monitoring
- ✅ **Modular sensor design** for easy expansion

### Software Features
- ✅ **Real-time data transmission** via WiFi
- ✅ **Python backend server** for data processing and storage
- ✅ **Kivy mobile application** for iOS/Android
- ✅ **Historical data logging** and trend analysis
- ✅ **Customizable alert thresholds**
- ✅ **User-friendly dashboard** with graphs and metrics

---

## 🛠️ Technologies Used

### Hardware Components

| Component | Model | Purpose |
|-----------|-------|---------|
| **Microcontroller** | ESP8266 | WiFi-enabled control unit |
| **Temperature & Humidity Sensor** | DHT11 | Measures ambient temperature and humidity |
| **Air Quality Sensor** | MQ-135 | Detects harmful gases and air pollutants |
| **Sound Sensor** | Analog/Digital | Monitors noise levels |
| **Light Sensor** | LDR/Photoresistor | Measures ambient light intensity |
| **Power Supply** | 5V adapter | Powers the system |

### Software Stack

**Embedded Programming:**
- **Arduino C++** - Microcontroller firmware for ESP8266
- **Arduino IDE** - Development environment

**Backend:**
- **Python 3.x** - Server-side data processing
- **Flask/FastAPI** (optional) - REST API for data communication
- **SQLite/MySQL** - Data storage

**Mobile App:**
- **Kivy Framework** - Python-based cross-platform mobile app development
- **KivyMD** - Material Design components
- **Matplotlib** - Data visualization in mobile app

---

## 🏗️ System Architecture

```
┌─────────────────┐
│   Parrot Cage   │
│                 │
│  [Sensors]      │
│   - DHT11       │
│   - MQ-135      │
│   - Sound       │
│   - Light       │
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│   ESP8266       │
│  Microcontroller│
│                 │
│  - Read Sensors │
│  - WiFi Send    │
└────────┬────────┘
         │ WiFi
         ↓
┌─────────────────┐
│  Python Server  │
│                 │
│  - Receive Data │
│  - Store DB     │
│  - Process      │
└────────┬────────┘
         │ HTTP/WebSocket
         ↓
┌─────────────────┐
│  Kivy Mobile    │
│  Application    │
│                 │
│  - Display Data │
│  - Alerts       │
│  - History      │
└─────────────────┘
```

### Data Flow

1. **Sensors** → ESP8266 reads analog/digital values
2. **ESP8266** → Transmits data packets over WiFi to Python server
3. **Python Server** → Processes, validates, and stores sensor data
4. **Mobile App** → Retrieves data via HTTP requests and displays real-time metrics
5. **Alerts** → Triggers notifications when thresholds are exceeded

---

## 💻 Installation

### Prerequisites

**Hardware:**
- ESP8266 development board
- DHT11, MQ-135, sound sensor, light sensor
- Breadboard and jumper wires
- 5V power supply

**Software:**
- Arduino IDE (1.8.19 or higher)
- Python 3.8 or higher
- pip package manager

### Setup Instructions

#### 1. Hardware Assembly

**Sensor Connections to ESP8266:**

| Sensor | ESP8266 Pin | Notes |
|--------|-------------|-------|
| DHT11 Data | D4 (GPIO2) | Temperature & humidity |
| MQ-135 Analog | A0 | Air quality |
| Sound Sensor | D5 (GPIO14) | Noise detection |
| Light Sensor | D6 (GPIO12) | Ambient light |
| VCC (All) | 3.3V/5V | Power supply |
| GND (All) | GND | Common ground |

*Note: Refer to circuit diagram for detailed wiring.*

#### 2. Arduino Code Setup

1. **Install ESP8266 board support** in Arduino IDE:
   - Go to File → Preferences
   - Add URL: `http://arduino.esp8266.com/stable/package_esp8266com_index.json`
   - Tools → Board → Boards Manager → Install "esp8266"

2. **Install required libraries**:
   - DHT sensor library (Adafruit DHT)
   - ESP8266WiFi library (built-in)

3. **Upload Arduino code**:
   ```bash
   # Open "arduino code to get sesors data" file
   # Update WiFi credentials:
   const char* ssid = "YOUR_WIFI_SSID";
   const char* password = "YOUR_WIFI_PASSWORD";
   const char* serverIP = "YOUR_SERVER_IP";
   
   # Select Board: Tools → Board → ESP8266 Boards → NodeMCU 1.0
   # Upload to ESP8266
   ```

#### 3. Python Backend Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/zohaibsumbal786/IOT-project-parrot-monitoring-system.git
   cd IOT-project-parrot-monitoring-system
   ```

2. **Install Python dependencies**:
   ```bash
   pip install flask requests sqlite3 matplotlib pandas
   ```

3. **Run the Python server**:
   ```bash
   # Open "iot project pythin kivy app code" file
   python server.py
   ```

#### 4. Mobile App Setup

1. **Install Kivy**:
   ```bash
   pip install kivy kivymd matplotlib
   ```

2. **Run the Kivy app**:
   ```bash
   # Open "iot kivy app code" file
   python main.py
   ```

3. **Configure server connection** in the app settings with your server IP address.

---

## 📁 Project Structure

```
IOT-project-parrot-monitoring-system/
│
├── hardware/
│   └── arduino_code.ino          # ESP8266 firmware
│
├── backend/
│   ├── server.py                 # Python data server
│   ├── database.py               # Database operations
│   └── config.py                 # Configuration
│
├── mobile-app/
│   ├── main.py                   # Kivy app entry point
│   ├── screens/                  # App screens
│   └── widgets/                  # Custom widgets
│
├── docs/
│   ├── circuit_diagram.png       # Wiring diagram
│   └── sensor_specs.pdf          # Sensor specifications
│
├── requirements.txt              # Python dependencies
├── README.md                     # This file
└── .gitignore
```

---

## 🔄 Usage

### Running the Complete System

1. **Power on hardware**:
   - Connect ESP8266 to power supply
   - Ensure all sensors are properly connected
   - Check green LED on ESP8266 (indicates WiFi connection)

2. **Start Python server**:
   ```bash
   python backend/server.py
   ```
   Server will start on `http://0.0.0.0:5000`

3. **Launch mobile app**:
   ```bash
   python mobile-app/main.py
   ```

4. **Monitor data**:
   - View real-time sensor readings on dashboard
   - Check historical trends with graphs
   - Receive alerts for abnormal conditions

### Configuration

**Alert Thresholds (customize in server.py):**
```python
TEMPERATURE_MAX = 30  # °C
TEMPERATURE_MIN = 18  # °C
HUMIDITY_MAX = 70     # %
HUMIDITY_MIN = 40     # %
AIR_QUALITY_MAX = 400 # PPM
SOUND_LEVEL_MAX = 80  # dB
LIGHT_MIN = 200       # Lux
```

---

## 📈 Results and Demonstration

### System Capabilities

- **Sensor Accuracy**:
  - Temperature: ±2°C
  - Humidity: ±5%
  - Air quality: Analog PPM value
  - Real-time updates every 5-10 seconds

### Mobile App Screenshots

*[Screenshots would be placed here showing:]*
- Dashboard with live sensor data
- Historical trend graphs
- Alert notifications
- Settings panel

### Real-world Testing

The system has been tested in real parrot care environments with successful:
- ✅ Continuous 24/7 monitoring
- ✅ Accurate temperature and humidity tracking
- ✅ Air quality anomaly detection
- ✅ Sound level monitoring for distress signals
- ✅ Light cycle tracking for circadian rhythm management

---

## 🔮 Future Improvements

1. **Advanced Features**:
   - **Machine Learning**: Predictive health analytics from historical data
   - **Computer Vision**: Camera integration for behavioral monitoring
   - **Voice Recognition**: Parrot call analysis for distress detection
   - **IoT Cloud**: Integration with AWS IoT or Google Cloud IoT

2. **Hardware Enhancements**:
   - Add more sensors (CO2, particulate matter PM2.5)
   - Battery backup for power outages
   - Solar panel option for outdoor aviaries
   - Multiple sensor nodes for large spaces

3. **Software Improvements**:
   - Web dashboard for desktop monitoring
   - Multi-user support with role-based access
   - Export data to CSV/PDF reports
   - Integration with veterinary systems
   - Push notifications to mobile devices

4. **Scalability**:
   - Support multiple bird cages simultaneously
   - Cloud database for remote access
   - RESTful API for third-party integrations

---

## 🎓 Learning Outcomes

This project demonstrates:
- ✅ **IoT System Design**: End-to-end hardware-software integration
- ✅ **Embedded Programming**: Arduino C++ for microcontrollers
- ✅ **Sensor Integration**: Multi-sensor data collection and processing
- ✅ **Wireless Communication**: WiFi protocols with ESP8266
- ✅ **Backend Development**: Python server for data management
- ✅ **Mobile Development**: Cross-platform app with Kivy
- ✅ **Data Visualization**: Real-time and historical data graphs
- ✅ **Problem Solving**: Practical application for animal welfare

---

## 🔧 Troubleshooting

**ESP8266 not connecting to WiFi:**
- Verify SSID and password in Arduino code
- Check WiFi signal strength
- Ensure 2.4GHz WiFi (ESP8266 doesn't support 5GHz)

**Sensors reading incorrect values:**
- Check wiring connections
- Calibrate sensors (DHT11 warm-up time: 2 seconds)
- Verify power supply voltage (3.3V/5V compatibility)

**Mobile app not receiving data:**
- Confirm Python server is running
- Check server IP address configuration in app
- Ensure devices are on the same network
- Check firewall settings

---

## 🤝 Contributing

Contributions are welcome! Areas for contribution:
- Hardware: Additional sensor support
- Software: New mobile app features
- Documentation: Circuit diagrams, tutorials
- Testing: Real-world deployment feedback

---

## 📄 License

This project is open source and available for educational and personal use.

---

## 👤 Author

**Zohaib Ahmed Khan Sumbal**

- GitHub: [@zohaibsumbal786](https://github.com/zohaibsumbal786)
- LinkedIn: [Connect with me](#)

---

## 🙏 Acknowledgments

- **ESP8266 Community** for excellent documentation
- **Arduino Project** for the development platform
- **Kivy Project** for cross-platform mobile framework
- **Sensor manufacturers** (DHT, MQ-series) for datasheets

---

## 📚 References

- [ESP8266 Documentation](https://arduino-esp8266.readthedocs.io/)
- [DHT11 Sensor Datasheet](https://www.mouser.com/datasheet/2/758/DHT11-Technical-Data-Sheet-Translated-Version-1143054.pdf)
- [MQ-135 Sensor Guide](https://www.instructables.com/MQ135-Gas-Sensor/)
- [Kivy Framework](https://kivy.org/)

---

<div align="center">

### 🦜 Caring for our feathered friends with technology! 

*Built with passion for IoT and animal welfare*

</div>
