https://user-images.githubusercontent.com/90082259/132118398-2ea3cc83-20b3-4c44-abba-b5e0f04605eb.mp4

# PikaSor - Your Parking Companion
A Two Wheeler Reverse Parking Sensor which helps the two wheeler owners park easily without any aches while turning back!! 
This thought of Idea was from my Problem I am facing it everyday while I am riding my vehicle. 
![WhatsApp Image 2021-09-04 at 11 51 38](https://user-images.githubusercontent.com/90082259/132085114-c55f3d94-044f-4e33-a5fd-2dd410b4e6a9.jpeg)
![WhatsApp Image 2021-09-04 at 11 51 38 (1)](https://user-images.githubusercontent.com/90082259/132085133-0b443eeb-db63-413c-9573-0d044f710f8a.jpeg)
![WhatsApp Image 2021-09-04 at 11 51 39](https://user-images.githubusercontent.com/90082259/132085135-2843c8ce-b49b-4a09-88bf-09a3d726c28d.jpeg)


## This will help you for making a sensor with the help of Following List of Components:-

1. Arduino Nano (or) Arduino Uno
2. UV Sensor
3. Buzzer
4. Jumper Wires
5. 9V Battery
6. LED Bulb
7. 330 OHM Resistor

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

#### Note:-
1. Remeber to not make loose connections otherwise your Arduino get's short-circuited and get's damaged. Also, using a optimum voltage battery which best fits to the both Arduino and the Sensor.
2. Also, before connecting the components check the components as if they are rightly soldered or not and are not damaged.

# My Experience in this Project:-
I have made this project by facing a few obstacles which were very cruicial to occur to learn and make this Project successful. I have a intermediate knowledge in C-Language and the basic rules of it I have uploaded my C++ Code in my ARDUINO NANO by using ARDUINO IDE SOFTWARE. My Project *PIKASOR* needed more than 5 libraries where all of them are pre-included in this Software. Basically, I have faced a JAVA Exception error when the Sensor starts working. So I have made changes in my code and my downloaded libraries which made fit for the project to work.

Coming to the Electronics Part I was much excited in making the connections and felt Curious and Excited that about this will be successful. Finally!! I was very happy that I could learn more and more stuff like this and acheive success not only in this but also in my future projects.

I thank our Mentor:- Vijay Raghav Varada Sir for making not only me but other engineering students out there by insipiring and making them to make things innovative. Also, making us PAR the hurdles we faced in it.
