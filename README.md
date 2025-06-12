# 🔥 MQ2 Gas Sensor Monitoring System

This repository contains the Arduino code and documentation for an IoT project featuring the MQ2 gas sensor, designed for real-time smoke and gas level detection.

## 📝 Description

This system is engineered to monitor gas and smoke concentrations in an environment using an MQ2 smoke sensor. It provides immediate visual and audio feedback, alerting users when predefined hazardous levels are detected, and indicating safe conditions otherwise.

## 🏗️ Project Structure

The repository is organized as follows:

* **`MQ2.ino`**: The main Arduino sketch containing the program logic for sensor reading, threshold comparison, and output control.
* **`README.md`**: This file, providing a comprehensive overview of the project, setup instructions, and working principles.
* **(Optional: You might add a `docs/` folder for images like circuit diagrams, or a `report/` folder for the full report if it's not directly in the README)**

## 🚀 Getting Started

Follow these steps to set up and run the MQ2 Gas Sensor Monitoring System:

### Prerequisites

* Arduino IDE installed on your computer.
* An Arduino board (e.g., Arduino Uno).
* The components listed in the [Components Used](#components-used) section.

### Hardware Hookup (Circuit Diagram)

*(**Suggestion**: It would be highly beneficial to include a simple circuit diagram here. You can draw one using Fritzing or just a clear photo. If you add an image, create an `images/` or `docs/` folder and link to it.)*

**Example Text (if you add a diagram):**
A detailed circuit diagram is available in `docs/circuit_diagram.png`. Follow these connections:
* MQ2 Sensor A0 pin to Arduino Analog Pin A5
* MQ2 Sensor VCC to Arduino 5V
* MQ2 Sensor GND to Arduino GND
* Red LED Anode to Arduino Digital Pin 13 (with a current-limiting resistor)
* Green LED Anode to Arduino Digital Pin 12 (with a current-limiting resistor)
* Buzzer Positive to Arduino Digital Pin 11
* All LED and Buzzer grounds to Arduino GND

### Software Installation

1.  **Clone the repository:**

    ```bash
    git clone [https://github.com/vamshi-afk/MQ2-Gas-Sensor.git](https://github.com/vamshi-afk/MQ2-Gas-Sensor.git)
    ```
    
3.  **Navigate to the project directory:**

    ```bash
    cd MQ2-Gas-Sensor
    ```
    
5.  **Open the Arduino Sketch:**
    * Open the `MQ2.ino` file using the Arduino IDE.
6.  **Upload to Arduino Board:**
    * Connect your Arduino board to your computer.
    * Select the correct board and port from the `Tools` menu in the Arduino IDE.
    * Click the "Upload" button to compile and upload the code to your Arduino.

## ⚙️ How It Works (Working Principle)

The system operates based on continuous gas/smoke level monitoring and real-time feedback:

1.  **Sensor Operation:** The MQ2 smoke sensor, containing a tin dioxide ($SnO_2$) sensing element, detects various gases (e.g., LPG, propane, methane, alcohol, hydrogen, smoke). Its analog output (connected to Arduino's A5) generates a voltage directly proportional to the gas/smoke concentration.
2.  **Reading Sensor Values:** The Arduino continuously reads this analog voltage using `analogRead(smokeA0)`. The raw sensor value is also printed to the Serial Monitor for debugging and real-time observation.
3.  **Threshold Comparison:** The read sensor value is compared against a predefined `sensorThres` value. This threshold differentiates between safe and hazardous gas/smoke levels.
    * If `sensorValue > sensorThres`: Indicates a potentially dangerous concentration.
    * If `sensorValue <= sensorThres`: Indicates safe air quality.
4.  **Alert Mechanism:**
    * **Above Threshold:** The red LED is illuminated, and the buzzer emits an audible alarm, providing an immediate alert. The green LED is turned off.
    * **Below Threshold:** The green LED is illuminated, signifying a safe environment. Both the red LED and the buzzer remain off.
5.  **Continuous Monitoring:** The `loop()` function, with a `delay(100)` milliseconds, ensures continuous monitoring and quick response to changes in air quality.

## 🔌 Components Used

This project utilizes the following hardware components:

1.  **Arduino Board:** Serves as the central microcontroller, responsible for reading sensor data, processing logic, and controlling output devices.
2.  **MQ2 Smoke Sensor:** The primary sensing element for detecting various combustible gases and smoke. It provides an analog output.
3.  **Red LED:** A visual indicator that illuminates when hazardous gas/smoke levels are detected.
4.  **Green LED:** A visual indicator that illuminates when safe gas/smoke levels are detected.
5.  **Buzzer:** An audible alert device that sounds when gas/smoke levels exceed the safe threshold.
6.  **Resistors (e.g., 220 Ohm):** (Optional but recommended) Used in series with LEDs to limit current and prevent damage.
7.  **Connecting Wires:** For establishing electrical connections between all components and the Arduino.
8.  **Power Supply:** To power the Arduino board and connected components (e.g., USB cable from a computer or a dedicated power adapter).

## ✨ Features

* **Real-time Monitoring:** Continuous sensing of gas and smoke levels.
* **Dual Alert System:** Provides both visual (LEDs) and audible (buzzer) warnings.
* **Configurable Threshold:** The alert sensitivity can be adjusted by modifying the `sensorThres` value in the code.
* **Serial Monitor Output:** Displays raw sensor readings for debugging and analysis.
* **Simple & Effective:** A straightforward solution for basic air quality monitoring.

## 🎯 Applications

This smoke detection system is a practical solution for various scenarios:

* **Home Safety:** Early detection of smoke from fires or gas leaks (e.g., LPG from stoves).
* **Industrial Environments:** Monitoring for potentially hazardous gas leaks in factories or workshops.
* **Public Spaces:** General air quality monitoring in enclosed areas.
* **Educational Projects:** An excellent introductory project for learning about IoT sensors, Arduino programming, and basic alarm systems.

## 🤝 Contribution

Feel free to fork this repository, open issues, and submit pull requests. Any contributions to improve the code, documentation, or add new features are welcome!

## Acknowledgment

This project was completed in collaboration with [@srikark7](https://github.com/srikark7), and [@Ruthvik136](https://github.com/Ruthvik136), who each contributed significantly to its development.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
