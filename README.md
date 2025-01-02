# Parkez - Arduino-Based Automatic Parking System 🚗

Parkez is a smart parking system built using Arduino, designed to efficiently manage parking slots and provide a seamless user experience. This project uses an LCD screen, IR sensors, and a servo motor to monitor slot availability and control entry, making it a practical prototype for automated parking management.

## 📌 Features

- **Real-Time Slot Monitoring:** Displays the number of available parking slots on an LCD screen.
- **IR Sensors:** Detects vehicles entering and exiting the parking area.
- **Servo-Controlled Barrier:** Automatically opens and closes the barrier based on parking slot availability.
- **Overflow Handling:** Displays a "Parking Full" message when slots are unavailable.

## 🛠️ Hardware Components

- Arduino Uno
- LiquidCrystal I2C LCD (16x2)
- Servo Motor
- IR Sensors
- Miscellaneous: Jumper wires, breadboard, etc.

## 📂 How It Works

1. **Initialization:** The system initializes by displaying a welcome message.
2. **Entry Detection:** An IR sensor detects a vehicle at the entry. If slots are available, the barrier opens, and the slot count decreases.
3. **Exit Detection:** An IR sensor at the exit detects a vehicle leaving, increases the slot count, and resets the barrier.
4. **Overflow Management:** When no slots are available, a "Parking Full" message is displayed, and the barrier remains closed.

## 📋 Code Explanation

The code is written in Arduino C++ and integrates the following:

- **Servo Motor Control:** Opens and closes the barrier.
- **IR Sensors:** Detect entry and exit.
- **LCD Display:** Updates and displays real-time slot availability.

## 🎯 Applications

- Prototype for automated parking systems.
- Demonstration of IoT and embedded systems in smart city solutions.

## 🚀 Future Enhancements

- Integration with mobile applications for slot booking.
- Cloud-based parking data for larger systems.
- Enhanced security with RFID or QR code-based access.
