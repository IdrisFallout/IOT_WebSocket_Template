# IOT_WebSocket_Template
The project is mainly involved in showing how to setup a simple serial communication between an Arduino and an esp8266 development board

## Instructions
- Upload the [arduino code](ArduinoCode/ArduinoCode.ino) to your Arduino Uno development board
- Upload the [esp8266 code](esp8266Code/esp8266Code.ino) to your esp8266 dev board
- Wire the circuit as shown below.

![CIRCUIT...](images/circuit.PNG?raw=true "Optional Title")

> **Note** 
> Make sure you have disconnected the 2 boards to power before connecting the circuit

## Explanation
### [ArduinoCode](ArduinoCode/ArduinoCode.ino)
Here i chose to send ultrasonic sensor data but you can send any message.
This is the actual arduino template to send a simple message to the esp8266
```cpp
 // Arduino UNO code
 #define TRIGGER_PIN 6
#define ECHO_PIN 7

long duration;
int distance;

void setup() {
  pinMode(TRIGGER_PIN, OUTPUT);
  pinMode(ECHO_PIN, INPUT);
  Serial.begin(9600);
}

void loop() {
  digitalWrite(TRIGGER_PIN, LOW);
  delayMicroseconds(2);
  digitalWrite(TRIGGER_PIN, HIGH);
  delayMicroseconds(10);
  digitalWrite(TRIGGER_PIN, LOW);
  duration = pulseIn(ECHO_PIN, HIGH);
  distance = (duration / 2) / 29.1;
  Serial.println(distance);
  delay(100);
}


```
