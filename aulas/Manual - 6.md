# Manual da aula 6
Os alunos montarão o circuito de LEDs e através dos interruptores irão acendê-las, ressalta-se que a energia do circuito será provida por placas solares.

## Circuito do TinkerCad

## Componentes
[Clique aqui para ver o circuito](https://www.tinkercad.com/things/lSdZuybCTaN)
- 1x Arduino uno;
- 5x LEDs coloridas;
- 5x Resistores de 220 ohm;
- 1x Placa de ensaio;
- 1x Placa solar.

## Instruções
- Pegue o arduino e conecte com as leds;
- Conecte os fios das leds com a placa de ensaio;
- Segure o arduino e encaixe a placa solar de modo que a fotovoltaica forneça energia ao sistema. 

## Código
int inter1=2;

int inter2=3;

int inter3=4;

int verde=5;

int amarelo=6;

int vermelho=7;

int laranja=8;

int azul=9;

int on1=0;

int on2=0;

int on3=0;
  
void setup()
{
  //Definindo as LEDS
  
  pinMode(verde,OUTPUT);
  
  pinMode(amarelo,OUTPUT);
  
  pinMode(vermelho,OUTPUT);
  
  pinMode(laranja,OUTPUT);
  
  pinMode(azul,OUTPUT);
  
  //Interruptores
  
  pinMode(inter1,INPUT);
  
  pinMode(inter2,INPUT);
  
  pinMode(inter3,INPUT);
 
  Serial.begin(9600);
  
}
 
void loop()
{
  //Lendo os interruptores
  
  on1=digitalRead(inter1);
  
  on2=digitalRead(inter2);
  
  on3=digitalRead(inter3);
  
  
  //Verde - Interruptor 1
  
  if(on1==HIGH){
  
  	digitalWrite(verde,HIGH);
    
  }
 
  else{
  
    digitalWrite(verde,LOW);
    
    digitalWrite(laranja,LOW);
    
    digitalWrite(azul,LOW);
    
  }
  
  //Amarelo - Interruptor 2
  
  if(on2==HIGH){
  
  	digitalWrite(amarelo,HIGH);
    
  }
  
  else{
  
  	digitalWrite(amarelo,LOW);
    
  }
  
  //Vermelho - Interruptor 3
 
 if(on3==HIGH){
  
  	digitalWrite(vermelho,HIGH);
  }
  
  else{
  
  	digitalWrite(vermelho,LOW);
  }
  
  //Laranja e Azul 
  
  if(on1==HIGH){
  
    //Laranja - Interruptor 1 e 3
    
    if(on3==HIGH && on2==LOW){
    
    	digitalWrite(laranja,HIGH);
      
      	digitalWrite(azul,LOW);
        
    }
    
    //Azul - Interruptor 1 e 2
    
    if(on2==HIGH && on3==LOW){
    
    	digitalWrite(azul,HIGH);
      
      	digitalWrite(laranja,LOW);
        
    }
  }
  
 
}
 

