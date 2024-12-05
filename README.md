# Dual_Axis_Solar_Tracker
Dual axis solar tracking system with weather sensor

---

## **Project Overview**
The Dual Axis Solar Tracker is an embedded project that adjusts the solar panel's position in real-time to maximize energy collection. The system also displays the temperature, humidity, and rainfall on a LCD screen. In this project I will be using the Arduino Uno Rev3 microcontroller to collect data from the sensors and control the servo motors.

---

## **Features**
Dual-Axis Tracking: Adjusts the solar panel position along two axes (horizontal and vertical) for optimal sunlight.
Weather Monitoring: Use of sensors to detect environmental conditions like temperature, humidity, and rainfall.
Energy Efficiency: Maximizes solar energy harvested throughout the day.

---

## **Components**
- **Arduino Uno Rev3**: Microcontroller.
- **Solar Panel**: Captures solar energy to power the system.
- **LDRs**: Four sensors guide the tracker by detecting the direction of maximum sunlight intensity.
- **Servo Motors**: Two motors control the panel's movement along horizontal and vertical axes for dual-axis tracking.
- **DHT11 Sensor**: Measures temperature and humidity.
- **Raindrop Sensor**: Detects rainfall.
- **I2C LCD Display**: Displays real-time data, including temperature, humidity, and rainfall status.
- **Buck Converter DC-DC**: Regulates voltage by stepping down to the required levels for the components. 
- **TP4056**: Lithium-ion battery charging module for managing the rechargeable batteries.
- **Rechargeable Batteries (18650, 3.7V)**: Power storage solution for continuous operation.
- Jumper wires, breadboard, resistors and micro USB cable.
