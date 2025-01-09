// Code made by Matt Kubas Spring 2023
#include <LiquidCrystal.h>

const int rs = 12, en = 11, d4 = 5, d5 = 4, d6 = 3, d7 = 2;
LiquidCrystal lcd(rs, en, d4, d5, d6, d7);
int button1 = 27;
int button2 = 32;
int button3 = 40;
int button4 = 45;
int led[] = {1, 28, 33, 41, 46};
int onoff = 18;
int buttonReset = 19;
int i=0;
int jeff=0;
String team1 = "1-Fanatics"; // Team Names (I did not decide these)
String team2 = "2-Haters";
String team3 = "3-Addicts";
String team4 = "4-Subjects";

void setup() {
  // put your setup code here, to run once: 
  lcd.begin(16, 2);
pinMode(button1, INPUT_PULLUP);
pinMode(button2, INPUT_PULLUP);
pinMode(button3, INPUT_PULLUP);
pinMode(button4, INPUT_PULLUP);
pinMode(led[1], OUTPUT);
pinMode(led[2], OUTPUT);
pinMode(led[3], OUTPUT);
pinMode(led[4], OUTPUT);
pinMode(onoff, INPUT_PULLUP);
pinMode(buttonReset, INPUT_PULLUP);

}

void loop() {
  // put your main code here, to run repeatedly:
lcd.setCursor(0, 0);
lcd.print("WAITING");
if(digitalRead(onoff)==LOW){
 jeff = 1;  
}
if(digitalRead(onoff)==HIGH){
  jeff=0;
  i=0;
  digitalWrite(led[1], LOW);
  digitalWrite(led[2], LOW);
  digitalWrite(led[3], LOW);
  digitalWrite(led[4], LOW);

}
if(digitalRead(buttonReset)==LOW){
  i=0;
  digitalWrite(led[1], LOW);
  digitalWrite(led[2], LOW);
  digitalWrite(led[3], LOW);
  digitalWrite(led[4], LOW);
 
}
while(jeff==1)
{ if(digitalRead(onoff)==HIGH){
  redo();
  break;
}
if(digitalRead(buttonReset)==LOW){
  redo();
  lcd.clear();
  break;  
}
  if(i==0)
    {if(digitalRead(onoff)==HIGH){
  redo();
  break;
}
if(digitalRead(buttonReset)==LOW){
  redo();
  break;  
}
    lcd.clear();
    lcd.setCursor(1,0);
    lcd.print("READY");
    digitalWrite(led[1], HIGH);
    digitalWrite(led[2], HIGH);
    digitalWrite(led[3], HIGH);
    digitalWrite(led[4], HIGH); 
     }
  while (i==0)
    {if(digitalRead(onoff)==HIGH){
  redo();
  break;
}
if(digitalRead(buttonReset)==LOW){
  redo();
  break;  
}
     if (digitalRead(button1)==LOW)
        {i=1;
        lcd.clear();
        lcd.setCursor(1,0);
        lcd.print(team1);
        lcd.setCursor(0,1);
        break;}
     if (digitalRead(button2)==LOW)
       {i=2;
       lcd.clear();
       lcd.setCursor(1,0);
       lcd.print(team2);
       lcd.setCursor(0,1);
       break;}
     if (digitalRead(button3)==LOW)
        {i=3;
        lcd.clear();
        lcd.setCursor(1,0);
        lcd.print(team3);
        lcd.setCursor(0,1);
        break;}
     if (digitalRead(button4)==LOW)
        {i=4;
        lcd.clear();
        lcd.setCursor(1,0);
        lcd.print(team4);
        lcd.setCursor(0,1);
        break;}
    }
  
  digitalWrite(led[1], LOW);
  digitalWrite(led[2], LOW);
  digitalWrite(led[3], LOW);
  digitalWrite(led[4], LOW);
  

  if(i!=0)
    {if(digitalRead(onoff)==HIGH){
  redo();
  break;
}
if(digitalRead(buttonReset)==LOW){
  redo();
  break;  
}
      delay(125);
      digitalWrite(led[i], HIGH);
      delay(125);
      digitalWrite(led[i], LOW);
      delay(125);
      digitalWrite(led[i], HIGH);
      delay(125);
      digitalWrite(led[i], LOW);
      delay(125);
      digitalWrite(led[i], HIGH);
      delay(125);
      digitalWrite(led[i], LOW);
      delay(500);
      if(digitalRead(onoff)==HIGH){
  redo();
  break;
}
if(digitalRead(buttonReset)==LOW){
  redo();
  break;  
}
      digitalWrite(led[i], HIGH);//count 1
      lcd.setCursor(0, 1);
      lcd.print("       --       ");
      delay(500);
      if(digitalRead(onoff)==HIGH){
  redo();
  break;
}
if(digitalRead(buttonReset)==LOW){
  redo();
  break;  
}
      digitalWrite(led[i], LOW);
      delay(500);
      if(digitalRead(onoff)==HIGH){
  redo();
  break;
}
if(digitalRead(buttonReset)==LOW){
  redo();
  break;  
}
      digitalWrite(led[i], HIGH);//2
      lcd.setCursor(0, 1);
      lcd.print("      ----      ");
      delay(500);
      if(digitalRead(onoff)==HIGH){
  redo();
  break;
}
if(digitalRead(buttonReset)==LOW){
  redo();
  break;  
}
      digitalWrite(led[i], LOW);
      delay(500);
      if(digitalRead(onoff)==HIGH){
  redo();
  break;
}
if(digitalRead(buttonReset)==LOW){
  redo();
  break;  
}
      digitalWrite(led[i], HIGH);//3
      lcd.setCursor(0, 1);
      lcd.print("     ------     ");
      delay(500);
      if(digitalRead(onoff)==HIGH){
  redo();
  break;
}
if(digitalRead(buttonReset)==LOW){
  redo();
  break;  
}
      digitalWrite(led[i], LOW);
      delay(500);
      if(digitalRead(onoff)==HIGH){
  redo();
  break;
}
if(digitalRead(buttonReset)==LOW){
  redo();
  break;  
}
      digitalWrite(led[i], HIGH);//4
      lcd.setCursor(0, 1);
      lcd.print("    --------    ");
      delay(500);
      if(digitalRead(onoff)==HIGH){
  redo();
  break;
}
if(digitalRead(buttonReset)==LOW){
  redo();
  break;  
}
      digitalWrite(led[i], LOW);
      delay(500);
      if(digitalRead(onoff)==HIGH){
  redo();
  break;
}
if(digitalRead(buttonReset)==LOW){
  redo();
  break;  
}
      digitalWrite(led[i], HIGH);//5
      lcd.setCursor(0, 1);
      lcd.print("   ----------   ");
      delay(500);
      if(digitalRead(onoff)==HIGH){
  redo();
  break;
}
if(digitalRead(buttonReset)==LOW){
  redo();
  break;  
}
      digitalWrite(led[i], LOW);
      delay(500);
      lcd.setCursor(0,1);
      lcd.print("================");
    }

  delay(10);
  while(i!=0)
    {
      if(digitalRead(onoff)==HIGH){
  redo();
  break;
}
if(digitalRead(buttonReset)==LOW){
  redo();
  break;  
}   
      if(digitalRead(buttonReset)==LOW)
      {
        redo();
        break;
      }
    }
  }
}



void redo(){
    lcd.clear();
    i=0;
    jeff=0;
    digitalWrite(led[1], LOW);
    digitalWrite(led[2], LOW);
    digitalWrite(led[3], LOW);
    digitalWrite(led[4], LOW);
    
  }
