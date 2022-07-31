# Electrical-power-and-electronics.Push-Button
# Push Button and LED control with the Arduino.ino


# Hardware Required :
 •	Arduino Uno
 •	Relay DPDT
 •	LED
 •	Button
 •	Resistor
 •	Wires
 •	Breadboard
 •	Light bulb
 •	9V Battery
# Steps :
 •	LED attach to board .
 •	Resistor connect to LED's long leg ( + ).
 •	The wire connect to resistor's other leg .
 •	Wire connect to digital pin 2 from resistor.
 •	Wire connect to LED's short leg , after that wire connect to ground from LED.
 •	The button attach to board .
 •	Resistor connect to button leg .
 •	wire connect to resistor leg , after that wire connect ground from resistor .
 •	wire connect to button's other leg , after that connect to 5V from button .
 •	Wire connect to button's top leg , after that connect to digital pin4 from button .
 •	The negative line of the battery is connected directly to the bulb.
 •	The positive right is connected to the com and then enters the Nc bulb.
 
 # The Code :
 
 
 #define LED_PIN 2
 #define BUTTON_PIN 4
 #define Relay_PIN 7


byte lastButtonState = LOW;
byte ledState = LOW;



void setup() {
  pinMode(LED_PIN, OUTPUT);
  pinMode(BUTTON_PIN, INPUT);
  pinMode(Relay_PIN, OUTPUT);
}
void loop() {
  byte buttonState = digitalRead(BUTTON_PIN);
  if (buttonState != lastButtonState) {
    lastButtonState = buttonState;
    if (buttonState == LOW) {
      ledState = (ledState == HIGH) ? LOW: HIGH;
      digitalWrite(LED_PIN, ledState);
      digitalWrite(Relay_PIN, ledState);
    }
  }
}

# The simulation :
![image](https://user-images.githubusercontent.com/108256116/182019570-c6e03151-563c-4f83-91fb-2ba0de6d47da.png)

 
# Reference :
https://roboticsbackend.com/arduino-turn-led-on-and-off-with-button

