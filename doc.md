## Ponderada SEM 03 - Programação

***Parte 1: Montagem Física do Semáforo***
Você deve realizar a montagem física de um semáforo utilizando LEDs e resistores em uma protoboard. Os LEDs devem representar as cores vermelho, amarelo e verde, seguindo o esquema de um semáforo convencional.

***Para completar esta etapa:***
- Conecte corretamente os LEDs e resistores na protoboard conforme o esquema.
- Certifique-se de usar os resistores adequadamente para proteger os LEDs.
- Organize a disposição dos fios para garantir clareza e facilidade de visualização.

| Componente           | Quantidade | Descrição                                      |
|----------------------|------------|------------------------------------------------|
| Arduino Uno          | 1          | Microcontrolador para controlar o circuito     |
| Protoboard           | 1          | Placa de ensaio para montagem do circuito      |
| LED (Vermelho)       | 1          | Indicador de "Pare"                            |
| LED (Amarelo)        | 1          | Indicador de "Atenção"                         |
| LED (Verde)          | 1          | Indicador de "Siga"                            |
| Resistores (220Ω)    | 3          | Para limitar a corrente dos LEDs               |
| Botão (Push Button)  | 1          | Inicia o loop do semáforo                      |
| Resistor de Pull-down| 1 (10kΩ)   | Estabiliza o sinal do botão                    |
| Jumpers (fios)       | Vários     | Conexões entre componentes e Arduino           |

**Funcionamento do Circuito**
Para visualização, clique [nesse link](https://drive.google.com/file/d/12UDFAiMguDL-SL8oJ8cxMH1kHA0HryBC/view?usp=sharing).

***Parte 2: Programação e Lógica do Semáforo***
Você deve programar o comportamento do semáforo para alternar entre as fases vermelho, amarelo e verde, seguindo a lógica abaixo:
- 6 segundos no vermelho
- 2 segundos no amarelo
- 2 segundos no verde
- +2 segundos no verde (simulando um tempo adicional para pedestres terminarem a travessia)
- 2 segundos no amarelo

Esse ciclo deve ser repetido continuamente em um loop.

Para completar essa etapa:
- Escreva o código para controlar as luzes do semáforo com a temporização exata descrita.
- Teste o código e certifique-se de que as fases estão funcionando corretamente, com as transições e tempos esperados.

```cpp
// Definição dos pinos
const int LED1 = 10;
const int LED2 = 7;
const int LED3 = 2;

void setup() {
  // Configuração dos pinos como saída
  pinMode(LED1, OUTPUT);
  pinMode(LED2, OUTPUT);
  pinMode(LED3, OUTPUT);
  pinMode(5, INPUT);
  pinMode(10, OUTPUT);
}

// Função para acender o LED por um tempo específico
void acenderLED(int pino, int tempo) {
  digitalWrite(pino, HIGH);
  delay(tempo);
  digitalWrite(pino, LOW);
}

void loop() {
  if (digitalRead(5) == LOW) {

  acenderLED(LED1, 6000); // Acende o LED1 por 6 segundos
  delay(1000);             // Espera de 1 segundo
  
  acenderLED(LED2, 2000); // Acende o LED2 por 2 segundos
  delay(2000);            // Espera de 2 segundos
  
  acenderLED(LED3, 4000); // Acende o LED3 por 4 segundos
  delay(1000);            // Espera de 1 segundo

  acenderLED(LED2, 2000); // Acende o LED2 por 2 segundos
  delay(2000);            // Espera de 2 segundos
}}
```

***Parte 3: Avaliação de Pares***

Nesta atividade, todos os alunos serão ser avaliadores e avaliados.
Cada atividade deverá ser avaliada por pelo menos dois alunos segundo os critérios do barema

### Avaliador: Pablo Azevedo

| Critério                                                                                                 | Contempla (Pontos) | Contempla Parcialmente (Pontos) | Não Contempla (Pontos) | Observações do Avaliador |
|---------------------------------------------------------------------------------------------------------|--------------------|----------------------------------|--------------------------|---------------------------|
| Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores                | Até 3              | Até 1,5                            | 0                        |     3                      |
| Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo                  | Até 3              | Até 1,5                          | 0                        |                      3     |
| Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) | Até 3              | Até 1,5                          | 0                        |                      3     |
| Extra: Implmeentou um componente de liga/desliga no semáforo e/ou usou ponteiros no código | Até 1              |  Até 0,5                         | 0                        |                      1     |
|  |                                                             | |**Pontuação Total**|10 | |

### Avaliador: João Gabriel
| Critério                                                                                                 | Contempla (Pontos) | Contempla Parcialmente (Pontos) | Não Contempla (Pontos) | Observações do Avaliador |
|---------------------------------------------------------------------------------------------------------|--------------------|----------------------------------|--------------------------|---------------------------|
| Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores                | Até 3              | Até 1,5                            | 0                        |     3                      |
| Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo                  | Até 3              | Até 1,5                          | 0                        |                      3     |
| Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) | Até 3              | Até 1,5                          | 0                        |                      3     |
| Extra: Implmeentou um componente de liga/desliga no semáforo e/ou usou ponteiros no código | Até 1              |  Até 0,5                         | 0                        |                      1     |
|  |                                                             | |**Pontuação Total**|10 | |
