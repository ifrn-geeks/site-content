# Manual da dinâmica 3
A dinâmica dessa aula funcionará a partir do uso de um robô que desenha figuras geométricas, em especial, triângulos.

## Componentes
[Clique aqui para ver o circuito](https://www.tinkercad.com/things/7j9DCHqotjk)
- 1x Kit carrinho - Arduino;
- 1x Sensor ultrassônico.

## Instruções
- Monte o carrinho do kit arduino e conecte o sensor a ele.

## Código
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

