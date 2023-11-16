const int tilt = 2;
const int Led1 = 3;
const int Led2 = 4;
const int buzzer = 5;

void setup() {
  pinMode(tilt, INPUT);
  pinMode(Led, OUTPUT);
  pinMode(Led, OUTPUT);
  pinMode(buzzer, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int tiltState = digitalRead(tilt);

     Serial.println(tiltState);
     delay(500);
     
  if (tiltState == HIGH)
    {
    digitalWrite(Led1, HIGH);
    digitalWrite(Led2, LOW);
    tone(buzzer, 1000); 
    } 
  else 
   {
    digitalWrite(Led1, LOW);
    digitalWrite(led2, HIGH);
    noTone(buzzer);
  }
}
