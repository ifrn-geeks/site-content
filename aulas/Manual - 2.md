# Manual da aula 2
A dinâmica vai ser voltada para o uso de buzzers que transmistirão uma mensagem em código morse.

## Componentes
[CLique aqui para ver o circuito](https://www.tinkercad.com/things/astJNqeTH3u)
- 1x Arduino Uno;
- 2x 100 Ω Resistor;
- 1x Buzzer;
- 1x Botão;
- 1x Placa de ensaio.

## Instruções
- Pegue o arduíno e os fios e conecte-os à placa de ensaio;
- Após isso, ligue os fios ao buzzer e aos fios.

## Código
int pos = 0;
 
void setup()
{

  pinMode(A0, INPUT);
  
  pinMode(8, OUTPUT);
  
}
 
void loop()
{

  if (digitalRead(A0) == HIGH) {
  
    tone(8, 165, 100); 
    
  }
  
  delay(10);
  
}
