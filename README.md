# Exercicio_em_Casa_2-Contagem-de-pressionamentos-de-bot-o
-
# Arduino feito no Tinkercad
-
-
![Editing Components (6)](https://github.com/user-attachments/assets/919b2e45-498f-4aa1-80ad-7570dc156f00)
-
-
# Materiais
-
1 Fio de 10 k ohm,
1 Fio de 220 ohm,
1 Led, 1 Protobord, 
1 Botão.
-
# Código
-
-
const int buttonPin = 2;
const int ledPin = LED_BUILTIN;
int buttonPushCounter = 0;
int buttonState = 0;
int lastButtonState = 0;

void setup() {
  pinMode(buttonPin, INPUT);
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  buttonState = digitalRead(buttonPin);

  if (buttonState != lastButtonState) {
    if (buttonState == HIGH) {
      buttonPushCounter++;
      Serial.println("on");
      Serial.print("Number of button pushes: ");
      Serial.println(buttonPushCounter);
    } else {
      Serial.println("off");
    }
    delay(50);
  }

  lastButtonState = buttonState;
}
