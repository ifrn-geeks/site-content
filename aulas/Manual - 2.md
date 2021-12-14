---
nome: Curso básico de Arduíno
número: 2
matéria: Geografia
conteúdo_propedêutico: Redes de trasporte
descrição: Introdução ao Mundo Maker
slides: https://docs.google.com/presentation/d/1J6umxqqafGLMLCPCdloBklrk7hnCiPPe
tinkercard: https://www.tinkercad.com/things/astJNqeTH3u
---

A dinâmica vai ser voltada para o uso de buzzers que transmitirão uma mensagem em código morse.

# Componentes

- 1x Arduino Uno;
- 2x 100 Ω Resistor;
- 1x Buzzer;
- 1x Botão;
- 1x Placa de ensaio.

# Instruções

- Pegue o arduino e os fios e conecte-os à placa de ensaio;
- Após isso, ligue os fios ao buzzer e aos fios.

# Código

```c++
int pos = 0;
 
void setup() {
  pinMode(A0, INPUT);
  pinMode(8, OUTPUT);
}
 
void loop() {
  if (digitalRead(A0) == HIGH) {
    tone(8, 165, 100); 
  }
  
  delay(10);
}
```
