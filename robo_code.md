const int buttonPinF = 1;   // the number of the pushbutton pin
const int buttonPinB = 2;
const int buttonPinR = 3;
const int buttonPinL = 4;

const int ledPin1 = 9;
const int ledPin2 = 10;
const int ledPin3 = 11;
const int ledPin4 = 12;

int buttonStateF = 0;
int buttonStateB = 0;
int buttonStateR = 0;
int buttonStateL = 0;

void setup() {
  // initialize the out pin as an output:
  pinMode(ledPin1, OUTPUT);
  pinMode(ledPin2, OUTPUT);
  pinMode(ledPin3, OUTPUT); 
  pinMode(ledPin4, OUTPUT);
 
  
  // initialize the pushbutton pin as an input:
  pinMode(buttonPinF, INPUT);
  pinMode(buttonPinB, INPUT);
  pinMode(buttonPinR, INPUT);
  pinMode(buttonPinL, INPUT);
  
}
void loop() {
  // read the state of the pushbutton value:
  buttonStateF = digitalRead(buttonPinF);
  buttonStateB = digitalRead(buttonPinB);
  buttonStateR = digitalRead(buttonPinR);
  buttonStateL = digitalRead(buttonPinL);
  

  // check if the pushbutton is pressed. If it is, the buttonState is HIGH:
  if (buttonStateF == HIGH) {
    // turn forward on:
    digitalWrite(ledPin1, HIGH);
    digitalWrite(ledPin2, LOW);
    digitalWrite(ledPin4, HIGH);
    digitalWrite(ledPin3, LOW);
  } 
  else if (buttonStateB == HIGH)   {
    // turn rev off:
    digitalWrite(ledPin1, LOW);
    digitalWrite(ledPin2, HIGH);
    digitalWrite(ledPin4, LOW);
    digitalWrite(ledPin3, HIGH);
  }
  else if (buttonStateR == HIGH)  {
    // turn Right off:
    digitalWrite(ledPin1, LOW);
    digitalWrite(ledPin2, LOW);
    digitalWrite(ledPin4, HIGH);
    digitalWrite(ledPin3, LOW);
  } 
  else if (buttonStateL == HIGH)   {
    // turn rev off:
    digitalWrite(ledPin1, HIGH);
    digitalWrite(ledPin2, LOW);
    digitalWrite(ledPin4, LOW);
    digitalWrite(ledPin3, LOW);
  }
  else {
    // turn LED off:
    digitalWrite(ledPin1, LOW);
    digitalWrite(ledPin2, LOW);
    digitalWrite(ledPin4, LOW);
    digitalWrite(ledPin3, LOW);
  }
}
