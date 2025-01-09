#include <arduino-timer.h>

auto timer = timer_create_default();

int io0 = 9;
int io1 = 10;
int io2 = 11;
int io3 = 12;
int io4 = 13;
int yellow =0;   //Yellow
int lGreen = 1;  //L Green
int rGreen = 3;  //R Green
int blue = 4;  //Blue
int lRed = 5;  //L Red
int rRed = 6;  //R Red
// int but7 = 7;
// int but8 = 8;
int select1 = A5;
int select2 = A4;
int select3 = A3;
int select4 = A2;
bool function_to_call(void * /* optional argument given to in/at/every */) {
  digitalWrite(io0, HIGH);
  digitalWrite(io1, HIGH);
  digitalWrite(io2, HIGH);
  digitalWrite(io3, HIGH);
  digitalWrite(io4, HIGH);
    return true; // to repeat the action - false to stop
}

void setup() {
  // put your setup code here, to run once:
pinMode(io0, OUTPUT);
pinMode(io1, OUTPUT);
pinMode(io2, OUTPUT);
pinMode(io3, OUTPUT);
pinMode(io4, OUTPUT);
pinMode(yellow, INPUT_PULLUP);
pinMode(lGreen, INPUT_PULLUP);
pinMode(rGreen, INPUT_PULLUP);
pinMode(blue, INPUT_PULLUP);
pinMode(lRed, INPUT_PULLUP);
pinMode(rRed, INPUT_PULLUP);
// pinMode(but7, INPUT_PULLUP);
// pinMode(but8, INPUT_PULLUP);
pinMode(2, INPUT_PULLUP);
pinMode(select1, INPUT_PULLUP);
pinMode(select2, INPUT_PULLUP);
pinMode(select3, INPUT_PULLUP);
pinMode(select4, INPUT_PULLUP);
attachInterrupt(digitalPinToInterrupt(2), redo, RISING);
redo();
}

void loop() {
  // put your main code here, to run repeatedly:
timer.tick();

while(digitalRead(select1)==LOW){
  timer.tick();
    
  if(digitalRead(yellow) == LOW){
    bin(1,1,1,1,0);
    timer.in(191000, function_to_call);
    
  }
  if(digitalRead(blue)==LOW){
    bin(1,1,1,0,1);
    timer.in(31000, function_to_call);
    
  }
  if(digitalRead(rGreen)==LOW){
    bin(1,1,1,0,0);
    delay(100);
    redo();
  }
  if(digitalRead(lGreen)==LOW){
    bin(1,1,0,1,1);
    delay(100);
    redo();
  }
  if(digitalRead(lRed)==LOW){
    bin(1,1,0,1,0);
    delay(100);
    redo();
  }
  if(digitalRead(rRed)==LOW){
    bin(1,1,0,0,1);
    delay(100);
    redo();
  }
}
while(select2==LOW){
  if(digitalRead(yellow) == LOW){
    bin(1,1,0,0,0);
    delay(100);
    redo();
  }
  if(digitalRead(lGreen)==LOW){
    bin(1,0,1,1,1);
    delay(100);
    redo();
  }
  if(digitalRead(rGreen)==LOW){
    bin(1,0,1,1,0);
    delay(100);
    redo();
  }
  if(digitalRead(blue)==LOW){
    bin(1,0,1,0,1);
    delay(100);
    redo();
  }
  if(digitalRead(lRed)==LOW){
    bin(1,0,1,0,0);
    delay(100);
    redo();
  }
  if(digitalRead(rRed)==LOW){
    bin(1,0,0,1,1);
    delay(100);
    redo();
  }
}
while(select3==LOW){
  if(yellow == LOW){
    bin(1,0,0,1,0);
    delay(100);
    redo();
  }
  if(digitalRead(lGreen)==LOW){
    bin(1,0,0,0,1);
    delay(100);
    redo();
  }
  if(digitalRead(rGreen)==LOW){
    bin(1,0,0,0,0);
    delay(100);
    redo();
  }
  if(digitalRead(blue)==LOW){
    bin(0,1,1,1,1);
    delay(100);
    redo();
  }
  if(digitalRead(lRed)==LOW){
    bin(0,1,1,1,0);
    delay(100);
    redo();
  }
  if(digitalRead(rRed)==LOW){
    bin(0,1,1,0,1);
    delay(100);
    redo();
  }
}
while(select4==LOW){
  if(digitalRead(yellow) == LOW){
    bin(0,1,1,0,0);
    delay(100);
    redo();
  }
  if(digitalRead(lGreen)==LOW){
    bin(0,1,0,1,1);
    delay(100);
    redo();
  }
  if(digitalRead(rGreen)==LOW){
    bin(0,1,0,1,0);
    delay(100);
    redo();
  }
  if(digitalRead(blue)==LOW){
    bin(0,1,0,0,1);
    delay(100);
    redo();
  }
  if(digitalRead(lRed)==LOW){
    bin(0,1,0,0,0);
    delay(100);
    redo();
  }
  if(digitalRead(rRed)==LOW){
    bin(0,0,1,1,1);
    delay(100);
    redo();
  }
}

}
void bin(int e,int d,int c,int b,int a){
if(a==1)
  digitalWrite(io0, HIGH);
else if(a==0)
  digitalWrite(io0, LOW);
if(b==1)
  digitalWrite(io1, HIGH);
else if(b==0)
  digitalWrite(io1, LOW);
if(c==1)
  digitalWrite(io2, HIGH);
else if(c==0)
  digitalWrite(io2, LOW);
if(d==1)
  digitalWrite(io3, HIGH);
else if(d==0)
  digitalWrite(io3, LOW);
if(e==1)
  digitalWrite(io4, HIGH);
else if(e==0)
  digitalWrite(io4, LOW);
else{}
}


void redo() {
  digitalWrite(io0, HIGH);
  digitalWrite(io1, HIGH);
  digitalWrite(io2, HIGH);
  digitalWrite(io3, HIGH);
  digitalWrite(io4, HIGH);
  timer.cancel();
}
