# Desafio-Super-Trunfo-da-Estacio
Trabalho do curso de Si


1. Este trabalho consiste na implementação do jogo Super Trunfo, utilizando a linguagem C, com o tema Digimon. O objetivo é aplicar conceitos de programação estruturada, como:

Estruturas de dados (struct)

Manipulação de arrays

Uso de funções

Controle de fluxo (switch, if-else)

Geração de números aleatórios

O jogo permite que o usuário enfrente a CPU em batalhas baseadas em atributos (Ataque, Defesa, Velocidade, HP).

2. Desenvolvimento
2.1. Estruturas de Dados
c
typedef struct {
    char nome[50];
    int ataque;
    int defesa;
    int velocidade;
    int hp;
} Digimon;
Finalidade: Armazenar os dados de cada Digimon.

Campos:

nome: String com o nome do Digimon.

ataque, defesa, velocidade, hp: Atributos numéricos para batalha.

2.2. Baralho de Digimons
c
Digimon digimons[10] = {
    {"Agumon", 70, 50, 60, 100},
    {"Gabumon", 60, 70, 50, 90},
    // ...
};
Finalidade: Pré-definir 10 Digimons com seus atributos.

Método de Escolha: Os Digimons são selecionados aleatoriamente para o jogador e a CPU.

2.3. Funções
exibirDigimon(Digimon d)
c
void exibirDigimon(Digimon d) {
    printf("\n--- %s ---\n", d.nome);
    printf("Ataque: %d\n", d.ataque);
    // ...
}
Finalidade: Exibir os atributos de um Digimon formatados.

main()
Inicialização:

c
srand(time(NULL));  // Inicializa a semente para números aleatórios
Sorteio de Digimons:

c
digimonJogador = digimons[rand() % 10];  // Sorteia um índice de 0 a 9
Lógica de Batalha:

c
switch (atributo) {
    case 1:  // Ataque
        if (digimonJogador.ataque > digimonCPU.ataque) {
            printf("\nVocê venceu!\n");
        }
        // ...
}
3. Fluxograma
plaintext
  INÍCIO
    │
    ├─ Sorteia Digimon para Jogador e CPU
    │
    ├─ Exibe Digimon do Jogador
    │
    ├─ Menu de Atributos:
    │   1. Ataque
    │   2. Defesa
    │   3. Velocidade
    │   4. HP
    │
    ├─ Compara atributos escolhidos
    │   │
    │   ├─ Se jogador > CPU: Vitória
    │   ├─ Se jogador < CPU: Derrota
    │   └─ Se igual: Empate
    │
    └─ Exibe Digimon da CPU e resultado
4. Testes e Resultados
Caso de Teste	Entrada (Atributo)	Saída Esperada
Agumon (Ataque 70) vs Gabumon (Ataque 60)	1 (Ataque)	"Você venceu!"
Patamon (Defesa 60) vs Gatomon (Defesa 45)	2 (Defesa)	"Você venceu!"
Empate em HP	4 (HP)	"Empate!"
5. Conclusão
O programa atende aos requisitos propostos, demonstrando:

Organização: Uso de structs para modelar dados.

Lógica: Comparação de atributos com switch e if-else.

Interatividade: Menu simples via console.

Possíveis melhorias:

Adicionar um sistema de pontuação.

Implementar um baralho dinâmico (lendo de arquivo).

Incluir evolução de Digimons durante o jogo.

