#include <Servo.h>

const int tempPin = A0;

const int highTempSignal = 8;
const int emergencySignal = 6;

const int greenLED = 5;
const int redLED = 4;
const int buzzer = 10;
const int servoPin = 9;

Servo door;

void setup() {
  pinMode(highTempSignal, OUTPUT);
  pinMode(emergencySignal, INPUT);

  pinMode(greenLED, OUTPUT);
  pinMode(redLED, OUTPUT);
  pinMode(buzzer, OUTPUT);

  door.attach(servoPin);
  door.write(0);

  Serial.begin(9600);
}

void loop() {

  int sensorValue = analogRead(tempPin);

  float voltage = sensorValue * (5.0 / 1023.0);
  float temperature = (voltage - 0.5) * 100.0;

  if (temperature >= 50) {
    digitalWrite(highTempSignal, HIGH);
  } else {
    digitalWrite(highTempSignal, LOW);
  }

  int emergency = digitalRead(emergencySignal);

  Serial.print("Temperature: ");
  Serial.print(temperature);
  Serial.println(" C");

  if (emergency == HIGH) {

    digitalWrite(greenLED, LOW);
    digitalWrite(redLED, HIGH);
    digitalWrite(buzzer, HIGH);

    door.write(90);

  } else {

    digitalWrite(greenLED, HIGH);
    digitalWrite(redLED, LOW);
    digitalWrite(buzzer, LOW);

    door.write(0);
  }

  delay(200);
}
