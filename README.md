# IOT_WebSocket_Template
The project is mainly involved in showing how to setup a simple serial communication between an Arduino and an esp8266 development board

## Instructions
- Upload the [arduino code](ArduinoCode/ArduinoCode.ino) to your Arduino Uno development board
- Upload the [esp8266 code](esp8266Code/esp8266Code.ino) to your esp8266 dev board
- Wire the circuit as shown below.

![CIRCUIT...](images/circuit-with-sensor.PNG?raw=true "Optional Title")

> **Note** 
> Make sure you have disconnected the 2 boards to power before connecting the circuit

## Explanation
### [ArduinoCode](ArduinoCode/ArduinoCode.ino)
Here i chose to send ultrasonic sensor data but you can send any message.
This is the actual arduino template to send a simple message to the esp8266
```cpp
// Arduino UNO code
void setup() {
  // Initialize serial communication
  Serial.begin(9600);
}

void loop() {
  Serial.println("Hello from Arduino Uno");
  delay(1000);
}

```
