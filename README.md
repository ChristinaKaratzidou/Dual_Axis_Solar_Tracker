# Dual_Axis_Solar_Tracker
Dual axis solar tracking system with weather sensor

---

## **Project Overview**
The Dual Axis Solar Tracker is an embedded project that adjusts the solar panel's position in real-time to maximize energy collection. The system also displays the temperature, humidity, and rainfall on a LCD screen. In this project I will be using the STM32F401RE microcontroller to collect data from the sensors and control the servo motors.

---

## **Features**
Dual-Axis Tracking: Adjusts the solar panel position along two axes (horizontal and vertical) for optimal sunlight.
Weather Monitoring: Use of sensors to detect environmental conditions like temperature, humidity, and rainfall.
Energy Efficiency: Maximizes solar energy harvested throughout the day.

---

## **Components**
- **STM32F401RE**: Microcontroller.
- **Solar Panel**: Captures solar energy to power the system.
- **LDRs**: Four sensors guide the tracker by detecting the direction of maximum sunlight intensity.
- **Servo Motors**: Two motors control the panel's movement along horizontal and vertical axes for dual-axis tracking.
- **DHT11 Sensor**: Measures temperature and humidity.
- **Raindrop Sensor**: Detects rainfall.
- **I2C LCD Display**: Displays real-time data, including temperature, humidity, and rainfall status.
- **Buck Converter DC-DC**: Regulates voltage by stepping down to the required levels for the components. 
- **TP4056**: Lithium-ion battery charging module for managing the rechargeable batteries.
- **Rechargeable Batteries (18650, 3.7V)**: Power storage solution for continuous operation.
- Jumper wires, breadboard, resistors and USB cable.

---

## **Hardware Connections**
### **STM32F401RE**
- VIN (5V) → Buck Converter Output (+5V)
- GND → Common Ground

### **Solar Panel → TP4056**
- Solar Panel (+) → TP4056 IN+
- Solar Panel (-) → TP4056 IN-
- TP4056 OUT- → Common Ground
- 18650 Battery connects to B+ and B- on TP4056

### **LDRs (with 10kΩ voltage divider resistors)**
- Top-Right LDR → PA1 (ADC1_IN1)
- Top-Left LDR → PA4 (ADC1_IN4)
- Bottom-Right LDR → PA6 (ADC1_IN6)
- Bottom-Left LDR → PA7 (ADC1_IN7)
- All LDRs need 10kΩ pull-down resistors to GND
- Other end of LDRs → 3.3V

### **Servo Motors**
- X-axis Servo Signal → PB6 (TIM4_CH1)
- Y-axis Servo Signal →PB7 (TIM4_CH2)
- Servo VCC → 5V from Buck Converter
- Servo GND → Common Ground

### **DHT11**
- VCC → 3.3V
- DATA → PB0
- GND → Common Ground
- 4.7kΩ pull-up resistor between VCC and DATA

### **Raindrop Sensor**
- VCC → 3.3V
- DO (Digital Out) → PB1
- AO (Analog Out) → PA5 (ADC1_IN5)
- GND → Common Ground

### **I2C LCD Display**
- VCC → 3.3V
- GND → Common Ground
- SDA → PB9 (I2C1_SDA)
- SCL → PB8 (I2C1_SCL)

---

## **Software Setup**
1. Install **STMCubeIDE**
2. Confugure in **CubeMX**:
   - Set system clock to 84MHz
   - Configure I2C1 for LCD
   - Configure ADC1 for LDRs and rain sensor
   - Configure TIM3 for servo control (50Hz PWM)
   - Enable necessary GPIO pins
3. Create **New Header Files**:
   - lcd_i2c.h
   - dht11.h
   - servo.h
4. Create **New Source Files**:
   - lcd_i2c.c
   - dht11.c
   - servo.c
5. Run your code
