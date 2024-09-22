Name:R.Mokshitha

Company:CODTECH IT SOLUTIONS

ID:CT08DS8185

Domain:Embedded Systems

Duration:September 15 to October 15 2024

Mentor:Neela Santhosh Kumar

OVERVIEW OF PROJECT


![WhatsApp Image 2024-09-22 at 12 33 36_7eece296](https://github.com/user-attachments/assets/ff04c714-5a62-43dc-994b-16f70b48f81a)





This project involves interfacing a DHT (Digital Humidity and Temperature) sensor with an Arduino board to measure ambient temperature and humidity. The sensor readings are then displayed on an LCD screen or serial monitor.

Components Required

Arduino Board (e.g., Arduino Uno)

DHT Sensor (e.g., DHT11 or DHT22)

LCD Screen (optional)

Breadboard

Jumper Wires

USB Cable

DHT Sensor

The DHT sensor is a popular, low-cost sensor for measuring temperature and humidity. There are two common versions:

DHT11: ±2°C temperature accuracy, 20-90% RH humidity accuracy

DHT22: ±0.5°C temperature accuracy, 0-100% RH humidity accuracy

Project Objectives

Interface DHT sensor with Arduino

Read temperature and humidity data from DHT sensor

Display readings on LCD screen or serial monitor

Monitor ambient temperature and humidity levels

Circuit Connection

Connect VCC pin of DHT sensor to Arduino's 5V pin

Connect GND pin of DHT sensor to Arduino's GND pin

Connect DATA pin of DHT sensor to Arduino's digital pin (e.g., D2)

Connect LCD screen's VCC, GND, SCL, and SDA pins to Arduino's corresponding pins (if using LCD)

Software Requirements

Arduino IDE

DHT library (install via Library Manager)

Code Overview

The code reads temperature and humidity data from the DHT sensor using the DHT library. It then displays the readings on the serial monitor or LCD screen.

Example Code:- const int analogIn = A0;

int humiditysensorOutput = 0;

// Defining Variables

int RawValue= 0;

double Voltage = 0;

double tempC = 0;

double tempF = 0;

void setup(){

Serial.begin(9600);

pinMode(A1, INPUT);

}

void loop(){

RawValue = analogRead(analogIn);

Voltage = (RawValue / 1023.0) * 5000; // 5000 to get millivots.

tempC = (Voltage-500) * 0.1; // 500 is the offset

tempF = (tempC * 1.8) + 32; // convert to F

Serial.print("Raw Value = " );

Serial.print(RawValue);

Serial.print("\t milli volts = ");

Serial.print(Voltage,0); //

Serial.print("\t Temperature in C = ");

Serial.print(tempC,1);

Serial.print("\t Temperature in F = ");

Serial.println(tempF,1);

humiditysensorOutput = analogRead(A1);

Serial.print("Humidity: "); // Printing out Humidity Percentage

Serial.print(map(humiditysensorOutput, 0, 1023, 10, 70));

Serial.println("%");

delay(5000); //iterate every 5 seconds

}

Project Applications

Weather monitoring stations

Indoor climate control systems

Greenhouse automation

Industrial process monitoring

Tips and Variations

Use a relay module to control heating/cooling systems based on temperature readings

Add a real-time clock module to log data with timestamps

Use Wi-Fi or Bluetooth modules to send data to online platforms or mobile apps

Experiment with different DHT sensor types and accuracy levels

This project provides a basic framework for temperature and humidity monitoring using DHT sensors and Arduino. You can expand upon this project by incorporating additional features and components.
