#include <LiquidCrystal_I2C.h>
LiquidCrystal_I2C lcd(0x27, 16, 2);
int  tiltsensor = 7;
int led1 = 3;
int led2 = 2;
int buzz = 6;

void setup (){
pinMode(tiltsensor, INPUT);
pinMode(led1, OUTPUT);
pinMode(led2, OUTPUT);
pinMode(buzz, OUTPUT);

  Serial.begin(9600);
 lcd.init();
 lcd.backlight();
}

void loop(){
  
  if (digitalRead(tiltsensor) ==HIGH)
{
lcd.setCursor(1, 0);
lcd.print("TILTED                          ");
lcd.setCursor(0, 1);
lcd.print("VALUE:  ");
lcd.print(digitalRead(tiltsensor));
digitalWrite(led1, HIGH);
digitalWrite(led2, LOW);
digitalWrite(buzz, HIGH);

}
else 
{
lcd.setCursor(1, 0);
lcd.print("NOT TILTED                   ");
lcd.setCursor(0, 1);
lcd.print("VALUE:  ");
lcd.print(digitalRead(tiltsensor));
digitalWrite(led1, LOW);
digitalWrite(led2, HIGH);
digitalWrite(buzz, LOW);

}
  delay(500);
}
