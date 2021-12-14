# Manual da aula 05
Os alunos deverão se reunir em grupos. Cada equipe irá precisar de um robô e um computador para programar o robô. A dinâmica acontecerá por rodadas, em cada rodada será dada uma sequência de passos de dança, utilizando os passos presentes na apresentação (drop, floss, dab e frash) um dos membros de cada grupo deverá dançar em um tempo limite, e os outros membros deverão memorizar a dança e programar o robô para repeti-la.

## Componentes
[Clique aqui para ver o circuito](https://www.tinkercad.com/things/7j9DCHqotjk)
- 2x Kit carrinho - Arduino;
- 2x Sensor ultrassônico.

## Instruções
- Conecte o sensor ao kit arduino montado.

## Passos de dança
- Drop: Dá um giro em 360°;
- Dab: Girar 90° para um lado e voltar para a posição inicial;
- Floss: Girar 90° um lado, andar para frente, girar 180° para o lado oposto, andar para frente, e voltar a posição inicial;
- Frash: Girar 90° para um lado, depois 180° para o lado inverso, e voltar a posição inicial.

## Código 
int pino_motor_direito_frente = 3;

int pino_motor_direito_tras = 5;

int pino_motor_esquerdo_frente = 6;

int pino_motor_esquerdo_tras = 9;

void setup() {
  pinMode(pino_motor_direito_frente, OUTPUT);
  pinMode(pino_motor_direito_tras, OUTPUT);
  pinMode(pino_motor_direito_frente, OUTPUT);
  
  pinMode(pino_motor_direito_tras, OUTPUT);
  
}

void mover_motor_direito_frente(int velocidade = 255) {
  
  analogWrite(pino_motor_direito_tras, 0);
  
  analogWrite(pino_motor_direito_frente, velocidade);
  
}

void mover_motor_direito_tras(int velocidade = 255) {
  
  analogWrite(pino_motor_direito_frente, 0);
  
  analogWrite(pino_motor_direito_tras, velocidade);
  
}

void parar_motor_direito() {
  
  analogWrite(pino_motor_direito_frente, 0);

  analogWrite(pino_motor_direito_tras, 0);
  
}

void mover_motor_esquerdo_frente(int velocidade = 255) {

  analogWrite(pino_motor_esquerdo_tras, 0);
  
  analogWrite(pino_motor_esquerdo_frente, velocidade);
  
}

void mover_motor_esquerdo_tras(int velocidade = 255) {
  
  analogWrite(pino_motor_esquerdo_frente, 0);
  
  analogWrite(pino_motor_esquerdo_tras, velocidade);
  
}

void parar_motor_esquerdo() {
  
  analogWrite(pino_motor_esquerdo_tras, 0);
  
  analogWrite(pino_motor_esquerdo_frente, 0);
  
}

void mover_para_frente(int velocidade = 255, int tempo) {
  
  mover_motor_direito_frente(velocidade);
  
  mover_motor_esquerso_frente(velocidade);
  
  delay(tempo);
  
  parar_motor1();
  
  parar_motor2();
  
}

void mover_para_tras(int velocidade = 255, int tempo) {
  
  mover_motor_direito_tras(velocidade);
  
  mover_motor_esquerdo_tras(velocidade);
  
  dalay(tempo);
  
  parar_motor1();
  
  parar_motor2();

}

void mover_para_direita(int tempo) {

  mover_motor_direito_tras(velocidade);
  
  mover_motor_esquerdo_frente(velocidade);
  
  delay(tempo);
  
  parar_motor1();
  
  parar_motor2();
  
}

void mover_para_esquerda(int velocidade, int tempo) {

  mover_motor_esquerdo_tras(velocidade);
  
  mover_motor_direito_frente(velocidade);
  
  delay(tempo);
  
  parar_motor1();
  
  parar_motor2();
  
}

// Será personalizado pelos alunos

void loop() {
  
}
