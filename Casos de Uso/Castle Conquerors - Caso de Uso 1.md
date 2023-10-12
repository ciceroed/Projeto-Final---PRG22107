# 1 - Caso de Uso: Jogar Castle Conquerors


## 1.1 Objetivo

Este caso de uso descreve a lógica principal do jogo Castle Conquerors.

## 1.2 Requisitos

Jogar Castle Conquerors.

## 1.3 Atores

Jogador.

## 1.4 Prioridade

Alta.

## 1.5 Pré-Condições

O jogo deve ser inicializado e criar um personagem inicial para o jogador e ter um conjunto de salas (masmorra) com desafios propostos.

## 1.6 Frequência de Uso

Não se aplica.

## 1.7 Criticalidade 

Alta.

## 1.8 Condição de Entrada

O jogador solicita o início de uma nova fase.

## 1.9 Fluxo Principal

1. O sistema cria o personagem para o jogador controlar;
2. O sistema cria um conjunto de salas que constituem a fase atual que o jogador deve passar;
3. A sala inicial é apresentada para o jogador, revelando os inimigos a serem derrotados;
4. O jogador seleciona uma ação a ser tomada em sua jogada;
5. O sistema verifica a ação:
    
    a. Caso seja uma ação de ataque, o sistema calcula o dano causado no inimigo selecionado.
    
    b. Caso seja utilizado um item, o sistema trata o efeito do item utilizado.
6. O sistema realiza as ações pré-definidas dos inimigos;
7. O sistema verifica o HP (Health Points) do jogador e dos inimigos:
    
    a. Se o HP do jogador chegou a zero o jogo é **finalizado**.
    
    b. Se todos os inimigos estão com HP zerado o jogador avança para a próxima sala.
    
    c. Se o jogador continua vivo e ainda restam inimigos o fluxo retorna para o item 4.


## 1.10 Fluxo Alternativo

Após a sala inicial, as salas seguintes podem apresentar diferentes comportamentos. Além de salas com inimigos, podem haver as seguintes salas:

1. Sala com um NPC (Non-Player Character) Mercador de itens;
2. Sala com um NPC curandeiro;
3. Sala com baú de tesouro;

Cada sala possui um fluxo alternativo diferente.

#### Sala com Mercador de Itens

1. O sistema cria o NPC mercador e seu inventário de itens;
2. O sistema apresenta a nova sala ao jogador;
3. O jogador seleciona se quer comprar itens ou avançar para a próxima sala;
4. Se o jogador seleciona comprar um item o sistema verifica se o jogador possui o dinheiro necessário.
    a. Se o jogador tem dinheiro suficiente, é descontado o valor do item e o mesmo é adicionado ao inventário do personagem.

    b. Se o jogador não tem dinheiro o suficiente o sistema informa que o valor é insuficiente para pagar pelo item.

5. Se o jogador seleciona avançar para a próxima sala, o sistema avança para a próxima sala.

#### Sala com Curandeiro

1. O sistema cria o NPC curandeiro;
2. O sistema apresenta a nova sala ao jogador;
3. O jogador interage com o curandeiro;
4. O sistema calcula o HP restaurado do jogador;
5. O jogador avança para a próxima sala.

#### Sala com Baú de Tesouro

1. O sistema cria um novo baú com tesouro aleatório;
2. O sistema apresenta a nova sala ao jogador;
3. O jogador decide entre interagir com o tesouro ou avançar para a próxima sala;
4. Se o jogador interagir com o tesouro, o sistema verifica o efeito do tesouro.
5. Se o jogador decidir avançar para a próxima sala, o sistema avança para a próxima sala.

## 1.11 Pós-Condições

Após o final de cada sala, os atributos do personagem do jogador devem estar atualizados de acordo com o resultado desta sala.

## 1.12 Regras de Negócio

1. O jogador é capaz de realizar apenas uma ação por turno.
2. Os desafios propostos devem estar de acordo com o nível atual do jogador.
3. A sala inicial de cada masmorra deve ser sempre uma sala com inimigos.


