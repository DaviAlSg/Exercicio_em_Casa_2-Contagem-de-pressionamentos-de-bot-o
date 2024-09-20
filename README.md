# Exercicio em Casa 2 Contagem de pressionamentos
-
# Arduino feito no Tinkercad
-
-
![image](https://github.com/user-attachments/assets/9aec8cb6-4954-4b27-b15a-700c0a322149)
-Para a montagem, é preciso conectar um botão ao pino D2 do Arduino, usando um resistor de 10kΩ para o GND,
O circuito contará quantas vezes o botão é pressionado. Conecte também os pinos de 5V e GND à protoboard para alimentação.
-
-
# Materiais
-
1 Fio de 10 k ohm,
1 Protobord, 
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
