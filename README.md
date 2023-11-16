// Define the pins for the tilt sensor, LEDs, and buzzer
const int tiltPin = 2;    // Connect the tilt sensor to digital pin 2
const int ledPin1 = 3;    // Connect the first LED to digital pin 3
const int ledPin2 = 4;    // Connect the second LED to digital pin 4
const int buzzerPin = 5;  // Connect the buzzer to digital pin 5

void setup() {
  pinMode(tiltPin, INPUT);
  pinMode(ledPin1, OUTPUT);
  pinMode(ledPin2, OUTPUT);
  pinMode(buzzerPin, OUTPUT);
}

void loop() {
  int tilting = digitalRead(tiltPin);  // Read the tilt sensor value
  
  if (tilting == HIGH) {
    digitalWrite(ledPin1, HIGH);  // Turn on the first LED
    digitalWrite(ledPin2, LOW);   // Turn off the second LED
    tone(buzzerPin, 1000);        // Generate a tone on the buzzer
  } else {
    digitalWrite(ledPin1, LOW);   // Turn off the first LED
    digitalWrite(ledPin2, HIGH);  // Turn on the second LED
    noTone(buzzerPin);            // Stop generating the tone
  }
}
