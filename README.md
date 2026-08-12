# 💡 Smart Automatic Street Light System using Arduino

This project is an automated street light controller that automatically turns an LED (Street Light) ON when darkness is detected and turns it OFF during daylight. It uses an LDR (Photoresistor) as a light sensor and an Arduino Uno as the main controller.

## 🛠️ Components Used
* Arduino Uno R3
* Breadboard
* LDR (Photoresistor)
* LED (Light Emitting Diode)
* 10K Ohm Resistor (for LDR)
* 220 Ohm Resistor (for LED)
* Jumper Wires

## 🔌 Circuit Connections
* **LDR Setup:** One leg to 5V (via Row 14), the other leg connected to Analog Pin A0 and pulled down to GND using a 10K Ohm Resistor (on Row 15).
* **LED Setup:** Anode (+) connected to Digital Pin 3 through a 220 Ohm Resistor (on Row 20), and Cathode (-) connected directly to GND (on Row 21).

## 💻 Arduino Source Code
```cpp
const int ldrPin = A0;  // LDR connected to Analog A0
const int ledPin = 3;   // LED connected to Digital Pin 3
int ldrValue = 0;       

void setup() {
  pinMode(ledPin, OUTPUT);  
  pinMode(ldrPin, INPUT);   
  Serial.begin(9600);       
}

void loop() {
  ldrValue = analogRead(ldrPin); 
  
  if (ldrValue < 500) {
    digitalWrite(ledPin, HIGH); // Turn ON LED in darkness
  } else {
    digitalWrite(ledPin, LOW);  // Turn OFF LED in light
  }
  delay(500); 
}
'''# Smart-Streeet-Light-Arduino-
