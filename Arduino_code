/************************************* MPMC Mini_Project***************************************/

const int s0 = 8;  
const int s1 = 9;  
const int s2 = 12;  
const int s3 = 11;  
const int out = 10; 

int redLed = 2;  
int greenLed = 3;  
int blueLed = 4;
int blackLed = 5;
int whiteLed = 6;
 
int red = 0;  
int green = 0;  
int blue = 0;  
    
void setup()   
{  
  Serial.begin(9600); 
  pinMode(s0, OUTPUT);  
  pinMode(s1, OUTPUT);  
  pinMode(s2, OUTPUT);  
  pinMode(s3, OUTPUT);  
  pinMode(out, INPUT);    
  digitalWrite(s0, HIGH);  
  digitalWrite(s1, HIGH);  
}  
    
void loop() 
{  
  color(); 
  Serial.print("R :");  
  Serial.print(red, DEC);  
  Serial.print(" G : ");  
  Serial.print(green, DEC);  
  Serial.print(" B : ");  
  Serial.print(blue, DEC);  
  //Serial.println();  

  if (red > blue && red > green && green > blue )
  {  
   Serial.println(" - (Blue Color)"); 
   
   digitalWrite(redLed, LOW);  
   digitalWrite(greenLed, LOW);  
   digitalWrite(blueLed, HIGH); // Turn BLUE LED ON 
   digitalWrite(blackLed, LOW);
   digitalWrite(whiteLed, LOW); 
  }  
  else if (green > red && green > blue && red > 55 )  
  {  
   Serial.println(" - (Black)");
   
   digitalWrite(redLed, LOW);  
   digitalWrite(greenLed, LOW);  
   digitalWrite(blackLed, HIGH); // Turn BLACK LED ON 
   digitalWrite(blueLed, LOW);
   digitalWrite(whiteLed, LOW);
  }

  else if (blue < red && blue < green && blue < 20)   
  {  
   Serial.println(" - (White)"); 
   
   digitalWrite(redLed, LOW);  
   digitalWrite(greenLed, LOW);  
   digitalWrite(whiteLed, HIGH); // Turn WHITE LED ON 
   digitalWrite(blackLed, LOW);
   digitalWrite(blueLed, LOW);   
  }  

  else if (blue > red && red < green && green > 55)   
  {  
   Serial.println(" - (Red Color)");  
   
   digitalWrite(blueLed, LOW);  
   digitalWrite(greenLed, LOW);  
   digitalWrite(redLed, HIGH); // Turn RED LED ON 
   digitalWrite(blackLed, LOW);
   digitalWrite(whiteLed, LOW);  
  }

  else if (green < red && green < blue && blue > green)  
  {  
   Serial.println(" - (Green Color)"); 

   digitalWrite(redLed, LOW);  
   digitalWrite(blueLed, LOW);  
   digitalWrite(greenLed, HIGH); // Turn GREEN LED ON 
   digitalWrite(blackLed, LOW);
   digitalWrite(whiteLed, LOW);
  }  
   
  else{
  Serial.println();
  }
  delay(300); 
  digitalWrite(redLed, LOW);  
  digitalWrite(greenLed, LOW);  
  digitalWrite(blueLed, LOW); 
  digitalWrite(blackLed, LOW);   
  digitalWrite(whiteLed, LOW);  
 }  
    
void color()  
{    
  digitalWrite(s2, LOW);  
  digitalWrite(s3, LOW);  
  //count OUT, pRed, RED  
  red = pulseIn(out, digitalRead(out) == HIGH ? LOW : HIGH);  
  digitalWrite(s3, HIGH);  
  //count OUT, pBLUE, BLUE  
  blue = pulseIn(out, digitalRead(out) == HIGH ? LOW : HIGH);  
  digitalWrite(s2, HIGH);  
  //count OUT, pGreen, GREEN  
  green = pulseIn(out, digitalRead(out) == HIGH ? LOW : HIGH);  
}
