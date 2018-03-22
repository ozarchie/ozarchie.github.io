# Smart Nutrient Pump

## Overview
This ESP32-nano project builds a fully automated nano-hydroponics dosing system utilizing online limit controls and as much recycling as possible.  

Software was developed using arduino-esp32 and is fully interrupt driven using a multi-cpu multi-task design methodology.

The system software is used to sense the water EC/PPM level and to control the peristaltic dosing pump. 

The system is built by recycling computer waste. The EC sensor is built from a simple soil moisture sensor. The nutrient pump is re-claimed from an inkjet printer.  

A display with EC/PPM and dosing provides local information.

The complete system is controlled online using Cayenne, where the EC/PPM limits and dosing levels are set.  

___

## Hardware

### Display
The display is a standard 2x40 LCD with I2C interface.

### EC / PPM
The EC/PPM sensor is constructed from a used AC round prong electrical lead. A standard two prong soil moisture sensor can also be used. The sensing is temperature compensated, and modulated to reduce fouling and corrosion.

### Relay
Standard relay-based controls allow for multiple types of pump interfaces. In the prototype, a recycled peristaltic pump was used for nutrient control.  

### Cabling
All cables are run using standard audio jacks.


___

## Software
All the software was designed using the Arduino ESP32 software development environment.  

Installation instructions and setup can be found here [arduino-esp32]  (https://github.com/espressif/arduino-esp32).

This document is maintained here [esp32-nano-pump]  (https://github.com/ozarchie/ozarchie.github.io).  

### Arduino
  The first part of the arduino software consists of two tasks that monitor the sensor or control the dosing pump. All these tasks are set to operate on processor zero.  
  
  - EC sensor
  - Pump

  The second part of the arduino software consists of two tasks that control the inputs and outputs of the smart pump communications. It also controls a display that shows the EC/PPM level and the dosing values. All these tasks are set to operate on processor one.  
     
 - Wifi
  
### Libraries
The arduino-esp32 contains libraries specific to the espressif esp32 architecture. These are selected when the ESP32 device is selected from the menu dropdowns. The following include identifies that the inbuilt libraries are to be preferred over others.  

```
#include <dummy.h>
```

### Special Libraries
The code contains special libraries that are specific to the hardware device and the espressif esp32 architecture. These are selected when the ESP32 device is selected from the menu dropdowns.

```
#include <LiquidCrystal_I2C.h>
#include <Ticker.h>
#include <WiFi.h>
#include <Cayenne.h>  
```

### Tasks

Tasks are enabled using the Ticker library.
### IOT

While IOT is *NOT* required for operation of the nano-hydroponics hardware, it facilitates modification of the limits that control its operation. A future extension of this project will allow direct control from a mobile phone or tablet. The IOT interface is used to set the control levels using the Wifi library and the Cayenne MQTT  interface. A Cayenne account is required for this operation.
___




