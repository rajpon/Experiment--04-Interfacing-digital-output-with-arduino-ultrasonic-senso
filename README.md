# EXPERIMENT-NO--04-Distance measurement using Ultrasonic sensor
 ###  DATE: 08/03/2024

###  NAME:M.ponraj 
###  ROLL NO :212221080055
###  DEPARTMENT: mechanical
## AIM: 
To interface an ultrasonic pair and measure the distance in centimeters , calculate the error
 
### COMPONENTS REQUIRED:
1.	ultrasonic sensor module HC-SR04
2.	1 KΩ resistor 
3.	Arduino Uno 
4.	USB Interfacing cable 
5.	Connecting wires 


### THEORY: 
The HC-SR04 ultrasonic sensor uses SONAR to determine the distance of an object just like the bats do. It offers excellent non-contact range detection with high accuracy and stable readings in an easy-to-use package from 2 cm to 400 cm or 1” to 13 feet.

The operation is not affected by sunlight or black material, although acoustically, soft materials like cloth can be difficult to detect. It comes complete with ultrasonic transmitter and receiver module.
Technical Specifications
Power Supply − +5V DC
Quiescent Current − <2mA
Working Current − 15mA
Effectual Angle − <15°
Ranging Distance − 2cm – 400 cm/1″ – 13ft
Resolution − 0.3 cm
Measuring Angle − 30 degree

The ultrasonic sensor uses sonar to determine the distance to an object. Here’s what happens:

The ultrasound transmitter (trig pin) emits a high-frequency sound (40 kHz).
The sound travels through the air. If it finds an object, it bounces back to the module.
The ultrasound receiver (echo pin) receives the reflected sound (echo).
The time between the transmission and reception of the signal allows us to calculate the distance to an object. This is possible because we know the sound’s velocity in the air. Here’s the formula:

distance to an object = ((speed of sound in the air)*time)/2
speed of sound in the air at 20ºC (68ºF) = 343m/s

### FIGURE 01 CIRCUIT OF INTERFACING ULTRASONIC SENSOR 


![image](https://github.com/rajpon/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-senso/assets/161028709/96b5d090-585e-4d9f-a5f7-9b7c670c428d)

![image](https://github.com/rajpon/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-senso/assets/161028709/943e5885-14e0-493f-8f5b-6356e3ee0d14)



### PROCEDURE:
1.	Connect the circuit as per the circuit diagram 
2.	Connect the board to your computer via the USB cable.
3.	If needed, install the drivers.
4.	Launch the Arduino IDE.
5.	Select the board (If you the board is arduino uno, select accordingly).
6.	Select your serial port, accordingly ( E.g. COM5 )
7.	Open the file of the program  and verify the error , clear if any errors that are existing 
8.	Upload the program and check for the physical working. 
9.	Ensure safety before powering up the device 
10.	Plot the graph for the output voltage vs the resistance 


### PROGRAM 
```
int echopin=6;

int trigpin=7;

int red=8;

int green=9;

long duration;

float distance;

void setup()

{

pinMode(echopin,INPUT);

pinMode(trigpin,OUTPUT);

pinMode(red,OUTPUT);

pinMode(green,OUTPUT);

Serial.begin(9600);

}

void loop()

{

digitalWrite(trigpin,LOW);

delay(10);

digitalWrite(trigpin,HIGH);

delay(10);

digitalWrite(trigpin,LOW);

duration=pulseIn(echopin,HIGH);

distance=duration*0.034/2;

Serial.print("distance=");

Serial.print(distance);

Serial.printIn("cms")

if(distance>50)

{

digitalWrite(green,HIGH);

delay(500);

digitalWrite(green,LOW);

delay(500);

}

}










`````````


### Distance vs measurement table 

			
 
			
			
			

![image](https://github.com/rajpon/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-senso/assets/161028709/d10fb4fa-317a-4040-a24f-5117c4bad762)

			
![image](https://github.com/rajpon/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-senso/assets/161028709/89d884ea-f361-4cef-8f33-99e19a062fd4)

			
			
			
			Average error = sum/ number of readings 
 
1. 0.12+0.13+0.41+0.65+0.68/5 = 0.398







### RESULTS
hence the interface of an ultrasonic pair and measurement of the distance in centimeters , calculation of the error was found


 
