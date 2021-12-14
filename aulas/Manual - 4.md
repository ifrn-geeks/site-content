# Manual da aula 4
A dinâmica consiste na montagem de um heredograma utilizando arduino.

## Componentes
[Clique aqui para ver o circuito](https://www.tinkercad.com/things/cZc2hi8WsCA)
- 1x Arduino Uno;
- 1x Placa de ensaio;
- 3x Resistor (1kΩ);
- 1x Resistor (470Ω );
- 3x Interruptores deslizantes;
- 5x LEDs;
  - De preferência coloridos;

## Instruções
- Com o arduino em mãos, comece a conectar as leds com os fios na protoboard;
- Após isso, conecte os cabos com os interruptores e com uma fonte elétrica;
- Ajuste os resistores de acordo com a fonte e a necessidade das LEDs.


##  Código
int bot1 = 2; //botão pai

 int bot2 = 3; //botão da mãe
 
 int bot3 = 9;//botão para sortear os genes dos filhos
 
 int Alelo_Pai_1;
 
 int Alelo_Pai_2; 
 
 int Alelo_Mae_1;
 
 int Alelo_Mae_2;
 
 int Filho0 = 8;
 
 int Filho1 = 6;
 
 int Filho2 = 10;
 
 int Filho[3];
 int cruzamento = 0;
 
 int numero = 10;
 
void setup(){
  
  
  pinMode(Filho0, OUTPUT); //led1
  
  pinMode(Filho1, OUTPUT); //led2
  
  pinMode(Filho2, OUTPUT); //led3
  
  pinMode(bot3, INPUT_PULLUP); //botão
  
 
 
  pinMode(3, OUTPUT);
  
  Serial.begin(9600);
  
 
  Alelo_Pai_2 = 0;
  
  Alelo_Mae_1 = 1;
  
  Alelo_Mae_2 = 1;
  
  
}
 
void loop(){
  
    Alelo_Pai_1 = digitalRead(bot1);
    
    //Visual com LEDS do sorteio
    
    while (digitalRead(bot3) == LOW) {
    
      // Cada LED liga e desliga o anterior.
      
      digitalWrite(Filho0, HIGH);
      
      delay(100); // Wait for 100 millisecond(s)
      
      digitalWrite(Filho1, HIGH);
      
      delay(100); // Wait for 100 millisecond(s)
      
      digitalWrite(Filho2, LOW);
      
      digitalWrite(Filho0, HIGH);
      
      delay(100); // Wait for 100 millisecond(s)
      
      digitalWrite(Filho1, LOW);
      
      digitalWrite(Filho2, HIGH);
      
      delay(100); // Wait for 100 millisecond(s)
      
      digitalWrite(Filho0, LOW);
      
      digitalWrite(Filho1, HIGH);
      
      delay(100); // Wait for 100 millisecond(s)
  
   
      // Quando chega no último, todos começam a ligar.   
      
      digitalWrite(Filho2, HIGH);
      
      delay(100); // Wait for 100 millisecond(s)
      
      digitalWrite(Filho1, HIGH);
     
     delay(100); // Wait for 100 millisecond(s)
     
     digitalWrite(Filho0, HIGH);
     
      delay(300); // Wait for 300 millisecond(s)
      
      // Todos desligam.
      
      digitalWrite(Filho0, LOW);
      
      digitalWrite(Filho1, LOW);
      
      digitalWrite(Filho2, LOW);
      
      delay(500); // Wait for 500 millisecond(s)
      
 
     //Filhos recebendo Genotipo    
      for(int i = 0; i < sizeof(Filho)/sizeof(Filho[0]); i++)
      {
    
        cruzamento = random(0, 3);
  
       if(cruzamento == 0){
       
         Filho[i] = Alelo_Pai_1 * Alelo_Mae_1;
  
       }else if(cruzamento == 1){
       
         Filho[i] = Alelo_Pai_2 * Alelo_Mae_1;
    
       }else if(cruzamento == 2){
       
         Filho[i] = Alelo_Pai_1 * Alelo_Mae_2;
    
       }else{
       
         Filho[i] = Alelo_Pai_2 * Alelo_Mae_2;
         
       }
      
       Serial.print("Cruzamento = ");
       
       Serial.println(cruzamento);
       
    
       Serial.print("Filho ");
       
       Serial.print(i);   
       
       Serial.println(Filho[i]);
       
 
     }
 
  }
 
 digitalWrite(Filho0, Filho[0]);
 
 digitalWrite(Filho1, Filho[1]);
 
 digitalWrite(Filho2, Filho[2]); 
  
}

