# Exercicio_em_Casa_2-Contagem-de-pressionamentos-de-bot-o
-
# Arduino feito no Tinkercad
-
-
![image](https://github.com/user-attachments/assets/d76ce0d8-bb8d-4097-9805-0ab2dc0f40d4)
-Para a montagem, é preciso conectar um botão entre o pino de 5V e o pino digital D2 do Arduino, utilizando um resistor de 10kΩ ligado ao GND.
Depois, ligue um LED, com o terminal positivo (ânodo) conectado ao pino digital D12 e o terminal negativo (cátodo) passando por um resistor de 220Ω até o GND.
Por fim, conecte os pinos de 5V e GND do Arduino à protoboard para fornecer energia ao circuito.
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
