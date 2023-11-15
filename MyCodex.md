const int tiltSensorPin = 2;
const int greenLedPin = 3;
const int redLedPin = 4;
const int buzzerPin = 5;

void setup() {
  pinMode(tiltSensorPin, INPUT);
  pinMode(greenLedPin, OUTPUT);
  pinMode(redLedPin, OUTPUT);
  pinMode(buzzerPin, OUTPUT);
}

void loop() {
  int tiltState = digitalRead(tiltSensorPin);

  if (tiltState == HIGH) {
    digitalWrite(greenLedPin, LOW);
    digitalWrite(redLedPin, HIGH);
    tone(buzzerPin, 1000);  // Adjust frequency as needed
  } else {
    digitalWrite(greenLedPin, HIGH);
    digitalWrite(redLedPin, LOW);
    noTone(buzzerPin);
  }
}
