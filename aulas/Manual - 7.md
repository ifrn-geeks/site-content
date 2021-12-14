# Manual da aula 07
A partir de itens recicláveis, os estudantes montarão um estacionamento, onde o robô irá entrar.

## Componentes
[Clique aqui para ver o circuito](https://www.tinkercad.com/things/kM4WFllKEmi)
- 3x LED;
- 1x Kit carrinho - Arduino;
- 1x Placa de ensaio;
- 1x Piezo;
- 3x 150Ω Resistor;
- 1x Sensor ultrassônico.

## Instruções
- Após o kit carrinho do arduino, conecte o piezo à placa de ensaio;
- Ainda segurando a placa, coloque as LEDs ligadas com os resistores;
- Por fim, conecte o sensor ultrassônico para medir a distância.

## Código
int distancia = 0;

int inicioP = 0;

int meioP = 0;

int fimP = 0;

int foraP = 0;

long readUltrasonicDistance(int triggerPin, int echoPin)
{

  pinMode(triggerPin, OUTPUT);  // para limpar o gatilho
  
  digitalWrite(triggerPin, LOW);
  
  delayMicroseconds(2);
  
  // Define o pino do gatilho para o estado ligado por 10 microsegundos
  
  digitalWrite(triggerPin, HIGH);
  
  delayMicroseconds(10);
  
  digitalWrite(triggerPin, LOW);
  
  pinMode(echoPin, INPUT);
  
  // Lê o pino de eco e retorna o tempo de viagem de onda sonora em microsegundos
  
  return pulseIn(echoPin, HIGH);
  
}

int counter;

int counter2;

void setup()
{

  pinMode(12, OUTPUT);
  
  pinMode(8, OUTPUT);
  
  pinMode(10, OUTPUT);
  
  pinMode(9, OUTPUT);
  
}

void loop()
{
  distancia = 0.01723 * readUltrasonicDistance(5, 6);
  
  foraP = constrain(distancia, 153, 327);
  
  if (distancia == foraP) {
  
    tone(12, 523, 200); // play tone 60 (C5 = 523 Hz)
    
    digitalWrite(10, HIGH);
    
    delay(200); // Wait for 200 millisecond(s)
    
    digitalWrite(10, LOW);
    
    noTone(12);
    
    delay(200); // Wait for 200 millisecond(s)
    
  } 
  else {
  
    digitalWrite(10, LOW);
    
  }
  
  distancia = 0.01723 * readUltrasonicDistance(5, 6);
  
  inicioP = constrain(distancia, 153, 327);
  
  if (distancia == inicioP) {
  
    digitalWrite(10, HIGH);
    
    for (counter = 0; counter < 1; ++counter) {
    
      tone(12, 523, 2000); // play tone 60 (C5 = 523 Hz)
      
      delay(1000); // Wait for 1000 millisecond(s)
      
      noTone(12);
      
      delay(1000); // Wait for 1000 millisecond(s)
      
    }
    
  }
  else {
  
    digitalWrite(10, LOW);
    
  }
  
  distancia = 0.01723 * readUltrasonicDistance(5, 6);
  
  meioP = constrain(distancia, 35, 150);
  
  if (distancia == meioP) {
  
    digitalWrite(10, LOW);
    
    digitalWrite(9, HIGH);
    
    for (counter2 = 0; counter2 < 1; ++counter2) {
    
      tone(12, 523, 1000); // play tone 60 (C5 = 523 Hz)
      
      delay(200); // Wait for 500 millisecond(s)
      
      noTone(12);
      
      delay(200); // Wait for 500 millisecond(s)
      
    }
    
  } 
  else {
  
    digitalWrite(9, LOW);
    
  }
  
  distancia = 0.01723 * readUltrasonicDistance(5, 6);
  
  fimP = constrain(distancia, 10, 30);
  
  if (distancia == fimP) {
  
    digitalWrite(9, LOW);
    
    digitalWrite(10, LOW);
    
    digitalWrite(8, HIGH);
    
    tone(12, 523, 500); // play tone 60 (C5 = 523 Hz)
    
    delay(500); // Wait for 500 millisecond(s)
    
    tone(12, 932, 500); // play tone 70 (A#5 = 932 Hz)
    
    delay(500); // Wait for 500 millisecond(s)
    
  } 
  else {
  
    digitalWrite(8, LOW);
    
  }
  
}

