# Nano Hydroponics

## Overview
This ESP32-nano project builds a fully automated nano-hydroponics system utilizing online limit controls and as much recycling as possible.  

Software was developed using arduino-esp32 and is fully interrupt driven using a multi-cpu multi-task design methodology.

The system software is used to sense -:  
 
1. the air temperature and humity
2. the water temperature and level
3. the water EC/PPM level
4. the water pH level
5. a lux meter

The system software is used to control -:  
 
1. the automated flow of nutirent enriched water
2. the hothouse air evacuation pump, or air heater
3. the water top-up valves
4. the water pH
5. the light level 

The system is built by recycling as much computer waste as possible. Th EC sensor is built from a surplus AC plug. The nutrient and pH pumps are re-claimed from an inkjet printer.  

The complete system is controlled online using Thingspeak, where the water, temperature, humidity, EC/PPM, pH and lux limits are set.  

A secondary project removes all the wiring by using ESP8266 to provide bluetooth wireless monitoring and control of the sensors pumps lighting and fans.

___

## Hardware
### Temperature
There are two temperature sensors in the project. The air temeprature is sensed using a DHT22. This controls the humidity level. The water temerature is  sensed using a DS18B20. It is used in conjunction with the EC/PPM sensor to compensate the EC/PPM levels.
### Humidity
The humidity is sensed using a DHT22 sensor. It is used in conjunction with the air temperature to control the humidity level.
### Water Level
The water level is sensed using a recycled water float and microswitch. It is used to control the nutrient water level.
### EC / PPM
The EC/PPM sensor is constructed from a used AC round prong electrical lead. A standard two prong soil moisture sensor can also be used. The sensing is temperature compensated, and modulated to reduce fouling and corrosion.
### Relays
Standard relay-based controls allow for multiple types of light, motor, pump and valve interfaces. In the prototype, recycled washing machine water valves and tap timers provided the water controls. A recycled peristaltic pump was used for nutrient control. A 12V automobile fan was used for humidity reduction. A 12V LED strip was used for lighting.  

The same interface could be used for SSR relays for AC powered fans, pumps and lights.

The interface also allows of-the-shelf bluetooth or wifi items to be used.
### Cabling
All cables are run using standard 3-pin 2.5mm stereo jacks.


___

## Software
All the software was designed using the Arduino ESP32 software development environment.  

Installation instructions and setup can be found here [arduino-esp32]  (https://github.com/espressif/arduino-esp32).

This document is maintained here [esp32-nano-hydro]  (https://github.com/ozarchie/ozarchie.github.io).
### Arduino
  The first part of the arduino software consists of seven tasks that monitor the sensors or control the inputs and outputs of the nano-hydropic installation. All these tasks are set to operate on processor zero.  
  
  1. LCD Display
  2. DHT air temperature and humidity sensor
  3. Onewire bus
  4. EC sensor
  5. Fans
  6. Pumps
  7. Lights

  The second part of the arduino software consists of two tasks that control the inputs and outputs of the nano-hydropic communications. All these tasks are set to operate on processor one.  
  1. Wifi
  2. Bluetooth
  
### Libraries
The arduino-esp32 contains libraries specific to the espressif esp32 architecture. These are selected when the ESP32 device is selected from the menu dropdowns. The following include identifies that the inbuilt libraries are to be preferred over others.  

```
#include <dummy.h>
```

### Special Libraries
The code contains special libraries that are specific to the hardware device and the espressif esp32 architecture. These are selected when the ESP32 device is selected from the menu dropdowns.

```
#include <OneWire.h>
#include <DallasTemperature.h>
#include <Wire.h> 
#include <DHTesp.h>
#include <LiquidCrystal_I2C.h>
#include <Ticker.h>
#include <WiFi.h>
#include <ThingSpeak.h>  
```

### Tasks

Tasks are enabled using the Ticker library.
### IOT

While IOT is *NOT* required for operation of the nano-hydroponics hardware, it facilitates modification of the limits that control its operation. A future extension of this project will allow direct control from a mobile phone or tablet. The IOT interface is used to set the control levels using the Wifi library and the Thingspeak MQTT  interface. A Thingspeak account is required for this operation.
___

## IOT
### Thingspeak
### Setup
### Limits
### Controls
___


## Tables

| EC | Description |
| ------ | ----------- |
| 100   | Water |
| 500 | Saltwater |



| PPM | Description |
| ------:| -----------:|
| 100  | Water |
| 500 | Saltwater |

