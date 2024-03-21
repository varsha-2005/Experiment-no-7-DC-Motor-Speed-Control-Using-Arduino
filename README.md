![image](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/36288975/739cc470-48c8-4873-a730-6319b4afc602)

###  DATE: 21-03-2024

###  NAME: VARSHA.G
###  ROLL NO : 212222230166
###  DEPARTMENT: AI-DS
# Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino
### AIM : To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

### Components Required:
•	Arduino UNO board
•	L293D driver
•	12V DC motor
•	10K ohm potentiometer
•	Pushbutton
•	12V source
•	Breadboard
•	Jumper wires
### THEORY 
The L293D quadruple half-H drivers chip allows us to drive 2 motors in both directions, with two PWM outputs from the Arduino we can easily control the speed as well as the direction of rotation of one DC motor. (PWM: Pulse Width Modulation).
Arduino DC motor control circuit:
Project circuit schematic diagram is the one below.

![Screenshot 2024-03-21 113612](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/119288183/f6a0fc56-b97e-4da8-a22d-3ec5847b7a14)


FIGURE-01 H BRIDGE CIRUCIT INTERFACE 
 
The speed of the DC motor (both directions) is controlled with the 10k potentiometer which is connected to analog channel 0 (A0) and the direction of rotation is controlled with the push button which is connected to pin 8 of the Arduino UNO board. If the button is pressed the motor will change its direction directly.
The L293D driver has 2 VCCs: VCC1 is +5V and VCC2 is +12V (same as motor nominal voltage). Pins IN1 and IN2 are the control pins where:

![Screenshot 2024-03-21 113734](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/119288183/98adc113-022d-4a57-820f-28b96ef04288)


TABLE-01 EXITATION TABLE FOR H BRIDGE 

As shown in the circuit diagram we need only 3 Arduino terminal pins, pin 8 is for the push button which toggles the motor direction of rotation. Pins 9 and 10 are PWM signal outputs, at any time there is only 1 active PWM, this allows us to control the direction as well as the speed by varying the duty cycle of the PWM signal. The active PWM pin decides the motor direction of rotation (one at a time, the other output is logic 0).

### PROGRAM 
```

int enable=2;
int input1=3;
int input2=4;
void setup()
{
  pinMode(enable, OUTPUT);
  pinMode(input1,OUTPUT);
  pinMode(input2,OUTPUT);
}
void loop()
{
  analogWrite(enable,255);
  delay(1000); 
  digitalWrite(input1,HIGH);
  digitalWrite(input2,LOW);
  delay(7000); 
  digitalWrite(input1,LOW);
  digitalWrite(input2,HIGH);
  delay(7000);
}

```
### OUTPUT

### GRAPH AND TABULATION 

![Screenshot 2024-03-21 113517](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/119288183/967975f0-4e54-4582-b8a3-e0541392e802)


![Screenshot 2024-03-21 113549](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/119288183/fbbf5934-bfab-4a56-91b3-13def91b0908)






### RESULTS AND DISCUSSION 

Thus we got the output To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

