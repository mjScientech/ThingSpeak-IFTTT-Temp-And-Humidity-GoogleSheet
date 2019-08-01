
## In this project, we will measure  temperature and Humidity using NCD  temperature and humidity sensor, ESP32, and ThingSpeak.We will also send different Temperature and Humidity readings to Google Sheet Using ThingSpeak and IFTTT  for analyzing Temp and Humidity  sensor data.
![alt tag](https://github.com/mjScientech/ThingSpeak-IFTTT-Temp-And-Humidity-GoogleSheet/blob/master/1.jpg)

**Hardware** :
- **[ESP-32](https://store.ncd.io/product/esp32-iot-wifi-ble-module-with-integrated-usb/)**:The ESP32 makes it easy to use the Arduino IDE and the Arduino Wire Language for IoT applications. This ESp32 IoT Module combines Wi-Fi, Bluetooth, and Bluetooth BLE for a variety of diverse applications. This module comes fully-equipped with 2 CPU cores that can be controlled and powered individually, and with an adjustable clock frequency of 80 MHz to 240 MHz. This ESP32 IoT WiFi BLE Module with Integrated USB is designed to fit in all ncd.io IoT products.Monitor sensors and control relays, FETs, PWM controllers, solenoids, valves, motors and much more from anywhere in the world using a web page or a dedicated server.We manufactured our own version of the ESP32 to fit into NCD IoT devices, offering more expansion options than any other device in the world! Integrated USB port allows easy programming of the ESP32. The ESP32 IoT WiFi BLE Module is an incredible platform for IoT application development. This ESP32 IoT WiFi BLE Module can be programmed using Arduino IDE.

- **[IoT Long Range Wireless  Temperature And Humidity  Sensor](https://store.ncd.io/product/industrial-long-range-wireless-temperature-humidity-sensor/)**:Industrial Long Range Wireless Temperature Humidity Sensor. Grade with a Sensor Resolution of ±1.7%RH ±0.5°C .Up to 500,000 Transmissions from 2 AA Batteries.Measures -40°C to 125°C with Batteries that Survive these Ratings.Superior 2-Mile LOS Range & 28 miles with High-Gain Antennas.Interface to Raspberry Pi, Microsoft Azure, Arduino and More

- **[Long Range Wireless Mesh Modem with USB Interface](https://store.ncd.io/product/900hp-s3b-long-range-wireless-mesh-modem-with-usb-interface/)**

**Software Used:**
- Arduino IDE
- ThingSpeak
- IFTTT

**Library Used:**
- PubSubClient Library
- Wire.h

# Arduino Client for MQTT
This library provides a client for doing simple publish/subscribe messaging with a server that supports MQTT

For more information about MQTT, visit [mqtt.org](http://mqtt.org/).
## Download
The latest version of the library can be downloaded from [GitHub](https://github.com/knolleary/pubsubclient/releases/tag/v2.7)
## Documentation
The library comes with a number of example sketches. See File > Examples > PubSubClient within the Arduino application.
Full [API Documentation](https://pubsubclient.knolleary.net/api.html).
## Compatible Hardware
The library uses the Arduino Ethernet Client api for interacting with the underlying network hardware. This means it Just Works with a growing number of boards and shields, including:

- Arduino Ethernet
- Arduino Ethernet Shield
- Arduino YUN – use the included YunClient in place of EthernetClient, and be sure to do a Bridge.begin() first
- Arduino WiFi Shield - if you want to send packets greater than 90 bytes with this shield, enable the [MQTT_MAX_TRANSFER_SIZE]  (https://pubsubclient.knolleary.net/api.html#configoptions) option in   PubSubClient.h.
- Sparkfun WiFly Shield – when used with [this](https://github.com/dpslwk/WiFly) library
- Intel Galileo/Edison
- ESP8266
- ESP32
The library cannot currently be used with hardware based on the ENC28J60 chip – such as the Nanode or the Nuelectronics Ethernet Shield. For those, there is an alternative library available.

# Wire Library
  The Wire library allows you to communicate with I2C devices, often also called "2 wire" or "TWI" (Two Wire Interface),can download  from [Wire.h](https://github.com/PaulStoffregen/Wire)
## Basic Usage
- Wire.begin()
  Begin using Wire in master mode, where you will initiate and control data transfers. This is the most common use when interfacing with   most I2C peripheral chips.

- Wire.begin(address)
  Begin using Wire in slave mode, where you will respond at "address" when other I2C masters chips initiate communication.
  
 ## Transmitting
 - Wire.beginTransmission(address)
   Start a new transmission to a device at "address". Master mode is used.

- Wire.write(data)
  Send data. In master mode, beginTransmission must be called first.

- Wire.endTransmission()
  In master mode, this ends the transmission and causes all buffered data to be sent.
  
## Receiving
- Wire.requestFrom(address, count)
  Read "count" bytes from a device at "address". Master mode is used.

- Wire.available()
  Retuns the number of bytes available by calling receive.

- Wire.read()
  Receive 1 byte.


##  Uploading the code  to ESP32 using Arduino IDE:

- **Before uploading the code you can view the working of this sensor at a given [link](https://github.com/ncdcommunity/Industrial-Wireless-IoT-Temperature-Humidity-Sensor?source=post_page---------------------------).**
- **Download and include the PubSubClient Library and Wire.h Library.**
- **You must assign your API key , SSID (WiFi Name) and Password of the available network.**
- **Compile and upload the  [Temp-ThinSpeak.ino](https://github.com/mjScientech/ThingSpeak-ESP32-and-Long-Range-Wireless-Temp-and-Humidity-Sensor/blob/master/Thingspeak_Temp.ino) code.**
- **To verify the connectivity of the device and the data sent, open the serial monitor.If no response is seen, try unplugging your ESP32 and then plugging it again. Make sure the baud rate of the Serial monitor is set to the same one specified in your code 115200.**

## Serial monitor output.
![alt tag](https://github.com/mjScientech/ThingSpeak-ESP32-and-Long-Range-Wireless-Temp-and-Humidity-Sensor/blob/master/serialmonitor.JPG)

## OUTPUT

![alt tag](https://github.com/mjScientech/ThingSpeak-ESP32-and-Long-Range-Wireless-Temp-and-Humidity-Sensor/blob/master/output1.JPG)

## Create an IFTTT Applet
- IFTTT is a web service that lets you create applets that act in response to another action. You can use the IFTTT Webhooks service to create web requests to trigger an action. The incoming action is an HTTP request to the web server, and the outgoing action is an email message.
- First create  an IFTTT account.
- Create an applet. Select My Applets.
![alt tag](https://github.com/mjScientech/Creating-Alert-using-ThingSpeak-ESP32-Long-Range-Wireless-Vibration-And-Temp/blob/master/event1.JPG)
-  Click the New Applet button.
 ![alt tag](https://github.com/mjScientech/Creating-Alert-using-ThingSpeak-ESP32-Long-Range-Wireless-Vibration-And-Temp/blob/master/event2.JPG)
 
- Select the input action. Click the word this.
 ![alt tag](https://github.com/mjScientech/Creating-Alert-using-ThingSpeak-ESP32-Long-Range-Wireless-Vibration-And-Temp/blob/master/event3.JPG)
  ![alt tag](https://github.com/mjScientech/Creating-Alert-using-ThingSpeak-ESP32-Long-Range-Wireless-Vibration-And-Temp/blob/master/event4.JPG)
 
 - Click  the Webhooks service. Enter Webhooks in the search field. Select the Webhooks.
  ![alt tag](https://github.com/mjScientech/Creating-Alert-using-ThingSpeak-ESP32-Long-Range-Wireless-Vibration-And-Temp/blob/master/event5.JPG)
 - Choose a trigger.
  ![alt tag](https://github.com/mjScientech/Creating-Alert-using-ThingSpeak-ESP32-Long-Range-Wireless-Vibration-And-Temp/blob/master/event6.JPG)
 - Complete the trigger fields. After you select Webhooks as the trigger, click the Receive a web request box to continue. Enter an event name.
   ![alt tag](https://github.com/mjScientech/Creating-Alert-using-ThingSpeak-ESP32-Long-Range-Wireless-Vibration-And-Temp/blob/master/event7.JPG)
    ![alt tag](https://github.com/mjScientech/Creating-Alert-using-ThingSpeak-ESP32-Long-Range-Wireless-Vibration-And-Temp/blob/master/event8.JPG)
  - Create trigger.
  - Now the trigger is created , for resulting action click That.
  ![alt tag](https://github.com/mjScientech/Creating-Alert-using-ThingSpeak-ESP32-Long-Range-Wireless-Vibration-And-Temp/blob/master/event9.JPG)
  -  Enter “Google Sheets”  in the search bar, and select the “Google Sheets”  box.
 ![alt tag](https://github.com/mjScientech/ThingSpeak-IFTTT-ESP32-Predictive-Machine-Monitoring/blob/master/sheets1.JPG)
 - If you have not connected to Google Sheet ,then connect it first.Now choose action.Select add a row to spreadsheet.
  ![alt tag](https://github.com/mjScientech/ThingSpeak-IFTTT-ESP32-Predictive-Machine-Monitoring/blob/master/sheets2.JPG)
 -  Then, complete the action fields.
  ![alt tag](https://github.com/mjScientech/ThingSpeak-IFTTT-Temp-And-Humidity-GoogleSheet/blob/master/google2.JPG)
 -  Your applet should be created after you press the Finish 
   ![alt tag](https://github.com/mjScientech/ThingSpeak-IFTTT-Temp-And-Humidity-GoogleSheet/blob/master/google1.JPG)
  - Retrieve your Webhooks trigger information. Select My Applets , Services and search for Webhooks. Click Webhooks and Documentation button. You see your key and the format for sending a request. Enter the event name. The event name for this example is VibrationAndTempData.You can test the service using the test button or by pasting the URL into your browser. 
  ![alt tag](https://github.com/mjScientech/ThingSpeak-IFTTT-ESP32-Predictive-Machine-Monitoring/blob/master/sheets6.JPG)
  ![alt tag](https://github.com/mjScientech/ThingSpeak-IFTTT-ESP32-Predictive-Machine-Monitoring/blob/master/timecontrol4.JPG)
  
 ## Create a MATLAB Analysis
  You can use the result of your analysis to trigger web requests, such as writing a trigger to IFTTT.
  - Click Apps , MATLAB Analysis and select New.
   ![alt tag](https://github.com/mjScientech/Creating-Alert-using-ThingSpeak-ESP32-Long-Range-Wireless-Vibration-And-Temp/blob/master/analysis1.JPG)
   ![alt tag](https://github.com/mjScientech/Creating-Alert-using-ThingSpeak-ESP32-Long-Range-Wireless-Vibration-And-Temp/blob/master/analysis2.JPG)
   
  -  Select Trigger Email from IFTTT in the Examples section. The code below is prepopulated in your MATLAB analysis window.
   ![alt tag](https://github.com/mjScientech/Creating-Alert-using-ThingSpeak-ESP32-Long-Range-Wireless-Vibration-And-Temp/blob/master/analysis3.JPG)
  - Name your analysis and modify the code.
 ![alt tag]()
  
  - Save your MATLAB Analysis. 
  
  ##  Create a Time Control to Run Your Analysis
  Evaluate your ThingSpeak channel data and trigger other events.
  - Click Apps,TimeControl, and then click New TimeControl.
    ![alt tag](https://github.com/mjScientech/Creating-Alert-using-ThingSpeak-ESP32-Long-Range-Wireless-Vibration-And-Temp/blob/master/analysis5.JPG)
    ![alt tag](https://github.com/mjScientech/Creating-Alert-using-ThingSpeak-ESP32-Long-Range-Wireless-Temp-And-Humidity/blob/master/timecontrol1.JPG)
    
   - Save your TimeControl.
    ![alt tag](https://github.com/mjScientech/Creating-Alert-using-ThingSpeak-ESP32-Long-Range-Wireless-Temp-And-Humidity/blob/master/timecontrol.JPG)

   
   ![alt tag](https://github.com/mjScientech/ThingSpeak-IFTTT-ESP32-Predictive-Machine-Monitoring/blob/master/timecontrol2.JPG)
# OUTPUT
- At last  data is  retrieved in Google Sheet.
![alt tag](https://github.com/mjScientech/ThingSpeak-IFTTT-Temp-And-Humidity-GoogleSheet/blob/master/sheetout.JPG)

   
 



