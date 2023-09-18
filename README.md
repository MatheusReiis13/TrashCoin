#include <Servo.h>
#define motor 11
int touch = 4;

Servo servo;

void setup()
{
  pinMode(touch, INPUT_PULLUP);
  pinMode(motor, OUTPUT);
  servo.attach(motor);
}

int pos = 0;

void loop()
{
  if (digitalRead(touch) == LOW)
  {
    for (pos = 0; pos <= 180; pos += 1)
    {
      servo.write(pos);
      delay(15);
    }
    for (pos = 180; pos >= 0; pos -= 1)
    {
      servo.write(pos);
      delay(15);
    }
  }
}
