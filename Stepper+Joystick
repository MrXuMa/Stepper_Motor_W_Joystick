#include <Stepper.h>

// Arduino pin numbers
const int stepsPerRevolution = 2048;  // change this to fit the number of steps per revolution
const int rolePerMinute = 17;         // Adjustable range of 28BYJ-48 stepper is 0~17 rpm
const int SW_pin = 2; // digital pin connected to switch output
const int X_pin = 0; // analog pin connected to X output
const int Y_pin = 1; // analog pin connected to Y output


// initialize the stepper library on pins 8 through 11:
Stepper myStepper(stepsPerRevolution, 8, 10, 9, 11);

void setup() {
  myStepper.setSpeed(rolePerMinute);
  pinMode(SW_pin, INPUT);
  digitalWrite(SW_pin, HIGH);
  // initialize the serial port:
  Serial.begin(9600);
}

void loop() {

    int xVar = analogRead(X_pin);

    if (xVar > 600)
    {
    Serial.println("Opening..");
    myStepper.step(stepsPerRevolution);
    delay(500);
    Serial.println("Open.");
    }
    

    if (xVar < 100)
    {
    Serial.println("Closing..");
    myStepper.step(-stepsPerRevolution);
    delay(500);
    Serial.println(xVar);
    }
