**Smart Health Monitoring IoT Platform**
This repository contains the implementation of a project for the course "IoT and Cloud for Sustainable Communities" as part of the master's program 
in "Digital Skills for Sustainable Societal Transitions" at Politecnico di Torino. The project focuses on developing an IoT platform designed for 
monitoring the health of elderly individuals, particularly those with conditions like Alzheimer's and dementia. The system is designed to alert 
caregivers in real-time in case of any irregularities in health or location, enhancing the safety and well-being of elderly individuals.
This project is an IoT-based Smart Health Monitoring Platform designed to monitor patients' vital signs such as heart rate and blood oxygen levels. 
The platform also includes GPS tracking functionality to ensure patients remain within a safe zone. The system provides real-time data visualization 
via ThingSpeak, and instant notifications via Telegram if any health metrics exceed dangerous thresholds.

**Features**
- Real-time Health Monitoring: The system tracks heart rate and blood oxygen levels.
- GPS Tracking: Monitors patients' location and alerts if they exit a predefined safe zone.
- Alert System: Sends alerts to users via Telegram if any health parameter crosses dangerous thresholds.
- Data Logging and Visualization: Logs data to ThingSpeak for long-term monitoring and visualization.
- Scalable MQTT Communication: Uses MQTT protocol for efficient data transmission between wearable devices and the monitoring system.

**Main Components**
1. WearableDevice.py
This script simulates a wearable device that continuously publishes heart rate, blood oxygen, and GPS data to an MQTT broker.
Key Features:
- Reads sensor data from CSV files.
- Publishes normal and critical data to appropriate MQTT topics.
- Simulates real-time data transmission by introducing delays between data points.

2. ThingSpeakAdaptor.py
This script subscribes to MQTT topics and logs the data to ThingSpeak for long-term monitoring and analysis.
Key Features:
- Subscribes to MQTT topics for heart rate and blood oxygen.
- Posts data to ThingSpeak using field mappings based on user IDs.
- Handles errors and logs the status of each data posting.

3. SmartHealthTelegram.py
This script runs a Telegram bot that provides users with real-time updates about their health metrics and GPS location.
Key Features:
- Allows users to log in and subscribe to health updates.
- Sends alerts if any health metric exceeds safe thresholds.
- Uses Telegram for user interaction and notifications.

**Getting Started**
Prerequisites
- Python 3.10
- A Telegram bot token (register your bot at BotFather)
- A ThingSpeak API key (sign up at ThingSpeak)

**Installation**
1. Clone the repository:
git clone https://github.com/Hesamedin2010/IoT-Platform-for-Elderly-Health-Monitoring.git
cd IoT-Platform-for-Elderly-Health-Monitoring

3. Install the required Python packages:
pip install -r requirements.txt

4. Set up your Catalog.json file to define users and their configurations.

**Running the Components**
1. Start the Wearable Device Simulation:
python WearableDevice.py

2. Start the ThingSpeak Adaptor:
python ThingSpeakAdaptor.py

3. Start the Telegram Bot:
python SmartHealthTelegram.py

**Directory Structure**
smart-health-monitoring/
│
├── Catalog.json                # Configuration file containing user information
├── WearableDevice.py           # Simulates a wearable device publishing data
├── ThingSpeakAdaptor.py        # Subscribes to MQTT topics and logs data to ThingSpeak
├── SmartHealthTelegram.py      # Telegram bot for user interaction and alerts
├── requirements.txt            # Python package dependencies
└── README.md                   # Project documentation

**Usage**
Telegram Bot Commands:
- /start - Start interaction with the bot.
- /login - Log in to the system.
- /latest - Get the latest health metrics.
- /stop - Stop receiving updates.

Data Monitoring:
- View real-time data on ThingSpeak (https://thingspeak.com/).
- Receive instant alerts on Telegram if any health metric is out of the safe range.

**License**
This project is licensed under the MIT License. See the LICENSE file for more details.

**Contributing**
Contributions are welcome! Please feel free to submit a Pull Request or open an issue for any improvements or bugs.
