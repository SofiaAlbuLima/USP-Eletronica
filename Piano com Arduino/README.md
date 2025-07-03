# Relatório do segundo projeto: Piano com Arduino
O segundo trabalho é um projeto livre utilizando Arduino, combinando software e hardware. Ele inclui o código-fonte feito no Software Arduino IDE, o circuito com todas as conexões, imagens do protótipo e um vídeo de demonstração explicando o funcionamento do sistema.

## Tabela de componentes usados & valores

| Componente | Especificação | Valor |
|------------|---------------|-------|
|1x Arduino|UNO R3 SMD|R$ 52,00|
|1x Protoboard|BB-01 400P|R$21,70|
|8x Chave Tátil 6x6x4|3mm 4 pinos|R$8,00|
|8x Resistor|CR25 220R|R$0,56|
|1x Buzzer|Passivo|R$9,70|
|65x Jumper (pacote)|Macho x Macho|R$20,00|
|Total:||R$111,96|

## Imagem do Projeto montado
![alt text](<midias/Circuito01.jpg>)

## Vídeo mostrando o Projeto Funcionando
https://youtu.be/U3GOM8prClg?feature=shared

## Imagens com todas as entradas do circuito
![alt text](<midias/Circuito02.jpg>)

## Código do Piano: Feito no Software Arduino IDE

```const int buzzer = 11;

const int botao_do0 = 2;
const int botao_re = 3;
const int botao_mi = 4;
const int botao_fa = 5;
const int botao_sol = 6;
const int botao_la = 7;
const int botao_si = 8;
const int botao_do1 = 9;

double do0 = 261.63; // frequência da nota dó
double re = 293.66; // frequência da nota ré
double mi = 329.63; // frequência da nota mi
double fa = 349.23; // frequência da nota fá
double sol = 392;   // frequência da nota sol
double la = 440;    // frequência da nota lá
double si = 493.88; // frequência da nota si
double do1 = 523;   // frequência da nota dó com uma oitava acima

void setup()
{
  pinMode(botao_do0, INPUT);
  pinMode(botao_re, INPUT);
  pinMode(botao_mi, INPUT);
  pinMode(botao_fa, INPUT);
  pinMode(botao_sol, INPUT);
  pinMode(botao_la, INPUT);
  pinMode(botao_si, INPUT);
  pinMode(botao_do1, INPUT);
  pinMode(buzzer, OUTPUT);
  Serial.begin(9600);
}

void loop()
{
  Serial.println(digitalRead(botao_do0));
  Serial.println(digitalRead(botao_re));
  Serial.println(digitalRead(botao_mi));
  Serial.println(digitalRead(botao_fa));
  Serial.println(digitalRead(botao_sol));
  Serial.println(digitalRead(botao_la));
  Serial.println(digitalRead(botao_si));
  Serial.println(digitalRead(botao_do1));

  if (digitalRead(botao_do0) == 1) {
    tone(buzzer, do0, 250);
  } else if (digitalRead(botao_re) == 1) {
    tone(buzzer, re, 250);
  } else if (digitalRead(botao_mi) == 1) {
    tone(buzzer, mi, 250);
  } else if (digitalRead(botao_fa) == 1) {
    tone(buzzer, fa, 250);
  } else if (digitalRead(botao_sol) == 1) {
    tone(buzzer, sol, 250);
  } else if (digitalRead(botao_la) == 1) {
    tone(buzzer, la, 250);
  } else if (digitalRead(botao_si) == 1) {
    tone(buzzer, si, 250);
  } else if (digitalRead(botao_do1) == 1) {
    tone(buzzer, do1, 250);
  } else {
    noTone(buzzer);
  }

  delay(10);
}
```
