---
nome: Curso Básico de Arduino: Comunicação na internet
número: 2
matéria: Português
conteúdo_propedêutico: Fake News
descrição: Discorrendo sobre a comunicação na internet e a presença de fake news
slides: https://docs.google.com/presentation/d/1J6umxqqafGLMLCPCdloBklrk7hnCiPPe
tinkercard: https://www.tinkercad.com/things/astJNqeTH3u  
---

# Objetivo da aula
Visa falar sobre a disciplina de português no que tange às fake news e discutir sobre artigos de opiniões, explicando a sua estrutura, trabalhando as competências EF89LP01, EF89LP02 e EF89LP03 da Base Nacional Comum Curricular, além disso, introduzir-será sobre condicionais ( if e else). Na parte técnica desta aula, os monitores farão uma dinâmica com um buzzer.


# Dinâmica
Os alunos serão divididos em dois grupos e a dinâmica vai ser voltada para o uso de buzzers que transmitirão uma mensagem em código morse.

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
