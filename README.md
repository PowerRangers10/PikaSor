# PikaSor
A Two Wheeler Reverse Parking Sensor which helps the two wheeler owners park easily without any aches while turning back.

## This will help you for making a sensor with the help of Following Componets:-
1] Arduino Nano (or) Arduino Uno
2] UV Sensor
3] Buzzer
4] Jumper Wires
5] 9V Battery

### Code for PikaSor:-
#define trig 12
#define echo 11
void setup() {

  pinMode(trig,OUTPUT);
  pinMode(echo,INPUT);
  pinMode(5, OUTPUT);
  pinMode(13, OUTPUT);
  Serial.begin(9600);
  
  

}

void loop() {

  
digitalWrite (trig,LOW);
delayMicroseconds(2);
digitalWrite (trig,HIGH);
delayMicroseconds(10);
digitalWrite (trig,LOW);


long t =pulseIn(echo,HIGH);

long cm = t/29/2;

Serial.println(cm);
delay (200);

digitalWrite (13, HIGH);
  delay (500);
  digitalWrite (13, LOW);
  delay (500);


if(cm <= 100 && cm >= 60 ){
  digitalWrite (5, HIGH);
  delay (100);
  digitalWrite (5, LOW);
  delay (1000);
}
else if (cm <= 50 && cm >=30){
   digitalWrite (5, HIGH);
  delay (100);
  digitalWrite (5, LOW);
  delay (500);
}
else if (cm <= 30 && cm >=10){
   digitalWrite (5, HIGH);
  delay (80);
  digitalWrite (5, LOW);
  delay (1);
}
else if (cm <= 10 && cm >=0){
   digitalWrite (5, HIGH);
  delay (50);
 // digitalWrite (6, LOW);
//  delay (50);
}
else {
 digitalWrite (5, LOW);
// delay (50);
}
}
