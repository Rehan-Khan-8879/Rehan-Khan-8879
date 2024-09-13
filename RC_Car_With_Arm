#include<Servo.h>

#define RightForward 2
#define RightBackward 3
#define LeftForward 4
#define LeftBackward 5 




char val;
int check = 1;

int Dmservo = 90;
int Dbservo = 0;
int Daservo = 20;
int Doservo = 140;

Servo mservo;
Servo aservo;
Servo bservo;
Servo oservo;

void setup(){
Serial.begin(9600);

bservo.attach(12);
aservo.attach(11);
mservo.attach(10);
oservo.attach(9);

pinMode(RightForward,OUTPUT);
pinMode(RightBackward,OUTPUT);
pinMode(LeftForward,OUTPUT);
pinMode(LeftBackward,OUTPUT);


bservo.write(Dbservo);
aservo.write(Daservo);
mservo.write(Dmservo);
oservo.write(Doservo);

}
void loop(){

  if(Serial.available()){
val = Serial.read();
Serial.println(val);

if(val == 'X'){
  check = 0;
}
if(val == 'x'){
  check = 1;
}

if(check == 1){
   car();
}
if(check == 0){
excavator();
}

}

}



void excavator(){

if(val == 'G'){
  Dbservo += 2;
  bservo.write(Dbservo);
}
if(val == 'I'){
Dbservo -=2;
bservo.write(Dbservo);
}
if(val == 'F'){
Daservo +=2;
aservo.write(Daservo);
}

if(val == 'B'){
  Daservo-=2;
  aservo.write(Daservo);
}

if(val == 'R'){
  Dmservo -=2;
  mservo.write(Dmservo);
}

if(val == 'L'){
  Dmservo +=2;
  mservo.write(Dmservo);
}


if(val == 'J'){
  Doservo +=2;
  oservo.write(Doservo);
}
if(val == 'H'){
  Doservo -=2;
  oservo.write(Doservo);

}

}


void car(){

if(val == 'F'){
  forward();
}
if(val == 'B'){
  backward();
}
if(val == 'R'){
  right();
}
if(val == 'L'){
  left();
}
if(val == 'S'){
  stop();
}
if(val == 'I'){
  right();
}
if(val == 'G'){
  left();
}
if(val == 'J'){
  left();
}
if(val == 'H'){
  right();
}

}

void forward(){
digitalWrite(RightForward,HIGH);
digitalWrite(LeftForward,HIGH);

digitalWrite(RightBackward,LOW);
digitalWrite(LeftBackward,LOW);
}

void backward(){
digitalWrite(RightForward,LOW);
digitalWrite(LeftForward,LOW);

digitalWrite(RightBackward,HIGH);
digitalWrite(LeftBackward,HIGH); 
}

void right(){
digitalWrite(RightForward,LOW);
digitalWrite(LeftForward,HIGH);

digitalWrite(RightBackward,HIGH);
digitalWrite(LeftBackward,LOW);
}

void left(){
digitalWrite(RightForward,HIGH);
digitalWrite(LeftForward,LOW);

digitalWrite(RightBackward,LOW);
digitalWrite(LeftBackward,HIGH);
}

void stop(){
digitalWrite(RightForward,LOW);
digitalWrite(LeftForward,LOW);

digitalWrite(RightBackward,LOW);
digitalWrite(LeftBackward,LOW);
}
