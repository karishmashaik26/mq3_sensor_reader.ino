# mq3_sensor_reader.ino

# 🍷 MQ3 Alcohol Sensor – Arduino Reader

This project reads alcohol levels using the **MQ3 gas sensor** and prints the scaled value to the serial monitor using an Arduino UNO.

---

## 🔧 Hardware Required

- Arduino UNO
- MQ3 Alcohol Sensor Module
- Jumper Wires

---

## 🔌 Connections

| MQ3 Sensor Pin | Arduino Pin |
|----------------|-------------|
| VCC            | 5V          |
| GND            | GND         |
| AOUT           | A0          |

---

## 🧪 Working

- The MQ3 sensor detects alcohol concentration in the air.
- The analog signal is read from pin `A0`.
- The code waits 20 seconds for sensor warm-up.
- Sensor values are printed every 2 seconds.

---

## code
#define MQ3pin 0

float sensorValue;
int x; // variable to store sensor value

void setup() {
  Serial.begin(9600); // sets the serial port to 9600
  Serial.println("MQ3 warming up!");
  delay(20000); // allow the MQ3 to warm up
}

void loop() {
  sensorValue = analogRead(MQ3pin);
  x = sensorValue / 30; // read analog input and scale it

  Serial.print("Sensor Value: ");
  Serial.println(x);

  delay(2000); // wait 2s for next reading
}


---

## 📈 Output Example

```text
MQ3 warming up!
Sensor Value: 10
Sensor Value: 12
Sensor Value: 14

