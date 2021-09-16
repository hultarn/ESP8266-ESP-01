# ESP8266-ESP-01
Base project for setting up the ESP8266 ESP-01 that will be used in future IoT appliactions

# Wiring
Since the ESP8266 ESP-01 isn't breadboard friendly I will be using an ESP8266 breakout board. I'll also be using an Arduino Uno. 

![](https://github.com/hultarn/ESP8266-ESP-01/blob/main/schematic_1.png)

Don't power the ESP8266 with 5V since it will ruin the board. The voltage divider is necessary since the Arduino Uno outputs 5V on it's digital outputs. The Ohm on the resistors doesn't really matters as long as they are the same.



# Setting up the ESP8266 and Arduino IDE
To work with the ESP8266 in the Arduino IDE I added the ESP8266 board by going into Settings->Additional Boards Manager URLs: and adding "http://arduino.esp8266.com/stable/package_esp8266com_index.json". Then under Tools->Board->Boards Manager I installed the esp8266 packet made by the ESP8266 Community, finally under Tools->Board I chose the "Generic ESP8266 Module"

Before outloading a Sketch to the ESP8266 I'll change the Baud Rate using AT commands, going from 115200 to 9600. To do this I opened the Serial monitor in the Arduino IDE, set the Baud Rate to 115200 and set the line breaks to both NL & CR. Finally I typed the following command "AT+UART_DEF=9600,8,1,0,0".

# Adding some wires
To get the Arduino to pass the Sketch to the ESP8266 I direcly connected the Arduinos RST pin to GND. To enter programming mode on the ESP8266 both it's RST pin and GP0 needs to be connected to GND. 

![](https://github.com/hultarn/ESP8266-ESP-01/blob/main/schematic_2.png)

# How to upload
Then when the Arduino IDE tries to connect to the ESP8266 I broke the connection between RST and GND and when a connection was made I broke the connection between GP0 and GND. I broke the connection manually but buttons could also have been used. 

# Final test
As a final test I tried the Blink Sketch under File->Examples->ESP8266->Blink with the following additional wires and LED. And with everything working I was done with this small project.
