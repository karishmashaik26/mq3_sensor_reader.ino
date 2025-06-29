# mq3_sensor_reader.ino
#define MQ3pin A0  // MQ3 sensor connected to analog pin A0

float sensorValue;

int x; // variable to store sensor value

void setup() {

  Serial.begin(9600); 
  // Initialize serial communication
  
  Serial.println("MQ3 warming up!");
  
  delay(20000);
  // Allow the MQ3 to warm up
}

void loop() {
  sensorValue = analogRead(MQ3pin);
  // Read analog value
  x = sensorValue / 30; 
  // Simple scaling for demo

  Serial.print("Sensor Value: ");
  Serial.println(x);

  delay(2000); 
  // Wait 2s for next reading
}
