# Smart-street-lightning
IoT based smart street lightning
This project is based on IoT.The basic idea behind this project is that whenever a vehicle passes over an LDR, the intensity of light falling on it reduces and as a result the corresponding LEDs turns on.
The main advantage of the project is energy saving. We can send this data over the cloud to calculate how much energy is conserved.
It is done with the help of LDR[light dependent resistor]. It is implemented on Arduino.
The code used is :-
int sensorPin1 = A0;
int sensorPin2 = A1;
int sensorPin3 = A2;
int sensorValue1 = 0;
int sensorValue2 = 0;
int sensorValue3 = 0;
void setup()
{  
  pinMode(5,OUTPUT);
  pinMode(6,OUTPUT);
  pinMode(7,OUTPUT);
  pinMode(8,OUTPUT);
  pinMode(9,OUTPUT);
  pinMode(10,OUTPUT);
  pinMode(11,OUTPUT);
  pinMode(12,OUTPUT);
  pinMode(13,OUTPUT);
  Serial.begin(9600);
}
void loop()
{
  sensorValue1 = analogRead(sensorPin1);
  Serial.print("Reading of LDR1=");
  Serial.println(sensorValue1);
  //delay(200);
  
  sensorValue2 = analogRead(sensorPin2);
  Serial.print("Reading of LDR2=");
  Serial.println(sensorValue2);
  //delay(200);
  sensorValue3 = analogRead(sensorPin3);
  Serial.print("Reading of LDR3=");
  Serial.println(sensorValue3);
 
  if(sensorValue1 <=1015)
  {
    digitalWrite(8,HIGH);
    digitalWrite(9,HIGH);
    digitalWrite(10,HIGH);
  }
  else
  {
    digitalWrite(8,LOW);
    
   digitalWrite(9,LOW);
   digitalWrite(10,LOW);
  }
   if(sensorValue2 <= 1015)
  {
    digitalWrite(11,HIGH);
    digitalWrite(12,HIGH);
    digitalWrite(13,HIGH);
  }
  else
  {
    digitalWrite(11,LOW);
    digitalWrite(12,LOW);
    digitalWrite(13,LOW);
  }
   if(sensorValue3 <= 1015)
  {
    digitalWrite(5,HIGH);
    digitalWrite(6,HIGH);
    digitalWrite(7,HIGH);
  }
  else
  {
    digitalWrite(5,LOW);
    digitalWrite(6,LOW);
    digitalWrite(7,LOW);
  }
}


    
