# GUARDIAN ANGEL: FALL DETECTION SYSTEM

## Project Overview

*Guardian Angel* is a real-time fall detection system designed to enhance personal safety for elderly individuals, solo travelers, and those at risk of falling without immediate assistance. Utilizing gyroscopic and accelerometric data from an MPU6050 sensor, the system detects falls accurately and initiates emergency responses when needed. The system also incorporates user confirmation to minimize false alerts and trigger emergency services only when necessary.

This prototype uses an ESP8266 microcontroller for processing and alerting, demonstrating its potential for integration into wearable devices like smartwatches and smartphones.

---

## Objective

The goal of this project is to:
- Detect falls in real-time using motion and acceleration data.
- Minimize false alarms through user confirmation mechanisms.
- Provide a scalable hardware solution that can be integrated into wearables.

---

## Dataset

While no external datasets are used, the system processes real-time sensor data from the MPU6050 module, including:
- **Acceleration Data**: To identify sudden changes in motion.
- **Angular Velocity Data**: To monitor orientation shifts.

---
## Flow Chart
<p align="center">
  <img src="https://github.com/user-attachments/assets/2a48f8b7-6e63-4496-a02e-8f08e155ddf1" alt="Fig 1. Flowchart of workflow" />
</p>

## Hardware Components
<p align="center">
  <img src="https://github.com/user-attachments/assets/0fbfd0ab-2065-4f45-91f0-fe1697bc022f" alt="Fig 2. Hardware connections" />
</p>

1. *MPU6050 Sensor*: Captures acceleration and angular velocity data.
2. *ESP8266 Microcontroller*: Processes sensor inputs and manages alerts.
    <p align="center">
      <img src="https://github.com/user-attachments/assets/43b4975c-53a3-4647-9de0-d2b1674cacfc" alt="Fig 3. Pin diagram of ESP8266" />
    </p>
4. *Buzzer & LED*: Indicate alerts and fall detection during testing.
   

## Technologies and Libraries Used

- **Hardware Components:**
  - MPU6050 Accelerometer and Gyroscope Sensor.
  - ESP8266 Microcontroller.
  - Buzzer and LED for testing alerts.

- **Programming Tools:**
  - Arduino IDE.
  - Libraries:
    - [Adafruit MPU6050](https://github.com/adafruit/Adafruit_MPU6050)
    - [Adafruit Sensor](https://github.com/adafruit/Adafruit_Sensor)

---

## Implementation

### Key Steps:
1. **Hardware Setup:**
   - Connect the *MPU6050* and *ESP8266* according to the wiring diagram in the image.

     <p align="center">
      <img src="https://github.com/user-attachments/assets/f28f1f37-8d50-4ee5-80f2-b99b418cc557" alt="Fig 4. Simulation showing connections of ESP8266 with MPU6050" />
     </p>


2. **Baseline Calibration:**
   - The system calculates baseline acceleration over a series of sensor readings during setup to establish a reference for detecting significant deviations.

3. **Fall Detection Logic:**
   - Thresholds are set for acceleration values to identify falls. A fall is detected when the current acceleration is significantly below the baseline and close to zero.
   - User confirmation is requested via the Serial Monitor to verify if the fall is real.

4. **Emergency Response:**
   - If the user does not respond within 10 seconds, local alerts (buzzer and LED) are activated, and emergency services are notified (to be implemented).

5. **Testing and Simulation:**
   - Logs from the Serial Monitor in Arduino IDE validate the system's performance.

---

## Results

- **Real-Time Fall Detection:** The system effectively identifies falls based on sensor thresholds and baseline calibration.
- **User Interaction:** The Serial Monitor allows users to confirm or dismiss falls, reducing false alerts.
- **Local Alerts:** Buzzer and LED provide immediate feedback during testing.

---

## Project Structure

|-- guardian_angel_fall_detection\
    |-- guardian_angel.ino\
    |-- results\
        |-- wiring_diagram.png\
        |-- simulation_screenshot.png\
    |-- README.md

---

## How to Run the Project

1. Clone the repository:

```bash

git clone https://github.com/username/guardian_angel.git

```

2. Install the required libraries in Arduino IDE:
   - Adafruit MPU6050
   - Adafruit Sensor

3. Connect the hardware:
   - Wire the MPU6050 sensor and ESP8266 according to the wiring diagram provided.

4. Upload the code:
   - Open `guardian_angel.ino` in Arduino IDE.
   - Select the correct board and port, and upload the code.

5. Test the system:
   - Use the Serial Monitor to observe fall detection and emergency responses.

---

## Future Enhancements

- **Mobile App Integration:** Connect with smartphones for alerts and location tracking.
- **GPS Support:** Enhance emergency response by including precise location data.
- **Machine Learning:** Develop advanced algorithms for improved fall detection accuracy.
- **Wearable Design:** Optimize for smartwatches and other portable devices.

---

## Conclusion

This project demonstrates the potential of sensor-based fall detection systems in ensuring personal safety. By leveraging accelerometric data and user confirmation, *Guardian Angel* provides a scalable and adaptable solution for real-time fall detection. Future iterations will focus on mobile integration, advanced algorithms, and expanded use cases for wearable technology.

## Contributing
We welcome contributions to make *Guardian Angel* more robust and accessible. You can:
- Report issues.
- Suggest new features.
- Submit pull requests.
