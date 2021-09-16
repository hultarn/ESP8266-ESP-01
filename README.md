# ESP8266-ESP-01
Base project for setting up the ESP8266 ESP-01 that will be used in future IoT appliactions

# Wiring
Since the ESP8266 ESP-01 isn't breadboard friendly I will be using an ESP8266 ESP-01 breakout board. I'll also be using an Arduino Uno. 



Don't power the ESP8266 ESP-01 with 5V since it will ruin the board. The voltage divider is necessary since the Arduino Uno outputs 5V on it's digital outputs.

Before outloading a Sketch to the ESP8266 ESP-01 I'll change the Baud Rate using AT commands, going from 115200 to 9600. To do this I opened the Serial monitor in the Arduino IDE, set the Baud Rate to 115200 and set the line breaks to both NL & CR. Finally I typed the following command "AT+UART_DEF=9600,8,1,0,0".

# Adding some wires
