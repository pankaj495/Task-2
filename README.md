// Smart Light Control System using LDR

int ldrPin = A0;   // LDR connected to A0
int ledPin = 2;    // LED connected to Pin 2

void setup() {
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {

  int ldrValue = analogRead(ldrPin);

  Serial.print("LDR Value = ");
  Serial.println(ldrValue);

  // Low Light -> LED ON
  if (ldrValue < 500) {
    digitalWrite(ledPin, HIGH);
    Serial.println("LED ON (Dark Environment)");
  }

  // Bright Light -> LED OFF
  else {
    digitalWrite(ledPin, LOW);
    Serial.println("LED OFF (Bright Environment)");
  }

  Serial.println("-------------------");

  delay(1000);
}
