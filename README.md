int RED    = 13;
int ORANGE = 12;
int GREEN  = 11;
int BLUE   = 10;
int BUTTON = 2;

bool blinking = false;
bool lastButtonState = LOW;
bool ledState = LOW;
unsigned long lastBlinkTime = 0;
int blinkInterval = 500;

void setup() {
  pinMode(RED,    OUTPUT);
  pinMode(ORANGE, OUTPUT);
  pinMode(GREEN,  OUTPUT);
  pinMode(BLUE,   OUTPUT);
  pinMode(BUTTON, INPUT);
}

void loop() {
  // Check button every loop
  bool currentButtonState = digitalRead(BUTTON);
  if (currentButtonState == HIGH && lastButtonState == LOW) {
    blinking = !blinking;  // Toggle
    delay(0);             // Debounce
    
    // Immediately turn off LEDs when stopping
    if (!blinking) {
      digitalWrite(RED,    LOW);
      digitalWrite(ORANGE, LOW);
      digitalWrite(GREEN,  LOW);
      digitalWrite(BLUE,   LOW);
      ledState = LOW;
    }
  }
  lastButtonState = currentButtonState;

  // Non-blocking blink using millis()
  if (blinking) {
    unsigned long currentTime = millis();
    if (currentTime - lastBlinkTime >= blinkInterval) {
      lastBlinkTime = currentTime;
      ledState = !ledState;  // Toggle LED state
      
      digitalWrite(RED,    ledState);
      digitalWrite(ORANGE, ledState);
      digitalWrite(GREEN,  ledState);
      digitalWrite(BLUE,   ledState);
    }
  }
}
