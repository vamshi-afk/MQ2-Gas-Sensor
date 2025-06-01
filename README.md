# MQ2-Gas-Sensor
This repository contains the code and report of the IOT project featuring the MQ2 gas sensor 

# DESCRIPTION:
This program is designed to monitor smoke or gas levels using a smoke sensor and provide visual and audio feedback based on the readings.

# Initialization (setup):
The setup function configures the LEDs and buzzer as output devices and the smoke sensor pin as input. It also initializes serial communication for monitoring sensor values.

# Main Loop (loop):
1. Reads the sensor's analog output using analogRead(smokeA0).
2. Prints the sensor value to the Serial Monitor for real-time observation.
3. Compares the sensor reading to the defined threshold (sensorThres).
4. If the reading exceeds the threshold:
   Activates the red LED (alert indicator) and buzzer.
   Turns off the green LED.
5. If the reading is below the threshold:
   Activates the green LED (safe indicator).
   Turns off the red LED and buzzer.
6. Adds a short delay (delay(100)) to stabilize the readings.

# COMPONENTS USED:
1. Arduino Board: Acts as the microcontroller to read sensor data, process it, and control outputs (LEDs and buzzer).
2. MQ2 Smoke Sensor: Detects gas or smoke levels. Outputs an analog signal corresponding to the concentration of gas/smoke.
3. Red LED: Alerts the user when the gas/smoke level exceeds the threshold.
4. Green LED: Indicates normal/safe gas or smoke levels.
5. Buzzer: Produces an audible alert when the gas/smoke level exceeds the threshold.
6. Resistors (Optional): Used with LEDs to limit current and prevent damage.
7. Connecting Wires: Connect the components to the Arduino.
8. Power Supply: Supplies power to the Arduino and connected components.

# CODE is in [MQ2.ino](MQ2.ino)

# Working Principle:
1. Sensor Operation: The smoke sensor (e.g., MQ-2) detects the presence of gas or smoke in the environment. Its analog output pin generates a voltage proportional to the concentration of the detected smoke or gas.
2. Reading Sensor Values: The Arduino reads the analog voltage from the sensor through pin A5 using the analogRead function. This value is printed to the Serial Monitor for monitoring.
3. Comparison to Threshold: If the sensor value exceeds the predefined threshold (sensorThres), it indicates the presence of smoke or gas above a dangerous level.
If the value is below the threshold, the air quality is considered safe.
4. Alert Mechanism:
  - Above Threshold: The red LED turns on, and the buzzer emits a sound to alert about the danger.
    The green LED is turned off to indicate an unsafe condition.
  - Below Threshold: The green LED turns on, signaling that the environment is safe.
    The red LED and buzzer remain off.
5. Loop and Delay: The loop repeats every 100 milliseconds to continuously monitor and respond to changes in air quality.

# Conclusion:
This smoke detection system demonstrates a simple yet effective way to monitor air quality and alert users to unsafe conditions. The circuit successfully performs the following:

1. Detects gas or smoke levels using the smoke sensor.
2. Provides real-time feedback through:
  LEDs (Green for safe, Red for alert).
  A buzzer for an audio alert.
3. Allows monitoring of sensor readings through the Serial Monitor.
  The system is practical for applications like:
  Home safety (e.g., fire detection).
  Industrial environments where gas leaks may occur.

Public spaces where air quality monitoring is required.
By adjusting the threshold value, this system can be tailored to detect specific levels of gas or smoke, making it versatile and adaptable to various use cases
