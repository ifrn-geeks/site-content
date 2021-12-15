---
nome: Curso Básico de Arduino: Robôs e triângulos
número:3
matéria: Matemática
conteúdo_propedêutico: Semelhanças de triângulos 
descrição: Aprofundamento do assunto de condicionais usando semelhança de triângulos
slides:https://docs.google.com/presentation/d/1f0zPImNHbkmD4ci3rfgqvSet5OqodA3V/edit?usp=sharing&ouid=117355551557473037768&rtpof=true&sd=true
tinkercard: https://www.tinkercad.com/things/7j9DCHqotjk
---

# Objetivo da aula
Visa falar sobre a disciplina de matemática no que tange à semelhança de triângulos, explicando os seus casos, trabalhando a competência EF09MA12 da Base Nacional Comum Curricular, além disso, aprofundar-ser-á sobre condicionais (if, else e else if). Na parte técnica desta aula, os monitores farão uma dinâmica com um robô carrinho.

# Dinâmica 3
Os alunos serão divididos em grupo e a dinâmica dessa aula funcionará a partir do uso de um robô carrinho que desenha figuras geométricas, em especial, triângulos.

## Componentes
- 1x Kit carrinho - Arduino;
- 1x Sensor ultrassônico.

## Instruções
- Monte o carrinho do kit arduino e conecte o sensor a ele.

## Código
```c++
int trig = 13; // pino transmissor
int echo = 12;	// pino receptor
 
int motor1=3;
int motor2=5;
 
float distancia,cm;	
 
 
void setup()	
{

  pinMode (trig, OUTPUT);
  
  pinMode (echo,INPUT);
  
  pinMode(motor1,OUTPUT);
  
  pinMode(motor2,OUTPUT)
  
  Serial.begin (9600);
  
}
 
//Função para ir reto

void reto(){

  digitalWrite(motor1, HIGH);
  
  digitalWrite(motor2, HIGH);
  
  delay(2000);
  
  digitalWrite(motor1, LOW);
  
  digitalWrite(motor2, LOW);
  
}
 
//Função para fazer uma curva

void curva(int t){

  digitalWrite(motor1, HIGH);
  
  digitalWrite(motor2, LOW);
  
  delay(t*1000);
  
  digitalWrite(motor1, LOW);
}
 
//Função que para os motores

void parada(int t){

  digitalWrite(motor1, LOW);
  
  digitalWrite(motor2, LOW);
  
  delay(t*1000);
  
}
 
//Desenhando um triângulo equilátero

void equilatero(){

  Serial.println("Andando reto");
  
  reto();
  
  Serial.println("Curva de 60 graus");
  
  curva(1);
  
  Serial.println("Andando reto");
  
  reto();
  
  Serial.println("Curva de 60 graus");
  
  curva(1);
  
  Serial.println("Andando reto");
  
  reto();
  
  Serial.println("Fim do triangulo");
  
  parada(2);
  
}
 
//Função para fazer um círculo

void circulo(){

  Serial.println("Realizando círculo");
  
  analogWrite(motor1,255);
  
  analogWrite(motor2,150);
  
  delay(5000);
  
  Serial.println("Fim de circulo");
  
  parada(2);
 
}
 
void loop()
{
  cm=calc();
  
  Serial.print(cm);
  
  Serial.println(" cm");

  
 if(cm<10){
 
  parada();
  
  }
  
  else{
  
  equilatero();
  
  }
  
}
 
//Cálculo da distância para evitar o robô de colidir

float calc(){

  //"zera" o sensor
  
digitalWrite(trig, LOW);

  delay(0005);
  
  //envio de pulso
  
  digitalWrite(trig, HIGH);
  
  delay(0010);
  
  digitalWrite(trig, LOW); //desliga o pulso
  
  distancia = pulseIn (echo, HIGH);   //interpretação do pulso para calcular a distância
  
  distancia = distancia/58;
  
  
  return distancia;
}
```
