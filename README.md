# Trabalho-desafio-xadrez
Trabalho desafio zadrez
#include <stdio.h>

// Define o tamanho do tabuleiro
#define TAMANHO 8

// Função para inicializar o tabuleiro (apenas com espaços vazios)
void inicializarTabuleiro(char tabuleiro[TAMANHO][TAMANHO]) {
    for (int i = 0; i < TAMANHO; i++) {
        for (int j = 0; j < TAMANHO; j++) {
            tabuleiro[i][j] = ' '; // Preenche com espaço vazio
        }
    }
}

// Função para exibir o tabuleiro
void exibirTabuleiro(char tabuleiro[TAMANHO][TAMANHO]) {
    printf("  a b c d e f g h\n"); // Coordenadas das colunas
    printf("-------------------\n");
    for (int i = 0; i < TAMANHO; i++) {
        printf("%d|", 8 - i); // Coordenadas das linhas (invertidas para visualização)
        for (int j = 0; j < TAMANHO; j++) {
            printf("%c|", tabuleiro[i][j]);
        }
        printf("\n-------------------\n");
    }
}

// Função para colocar uma peça no tabuleiro
// Linha e coluna são baseadas em 0-7 internamente
void colocarPeca(char tabuleiro[TAMANHO][TAMANHO], int linha, int coluna, char peca) {
    if (linha >= 0 && linha < TAMANHO && coluna >= 0 && coluna < TAMANHO) {
        tabuleiro[linha][coluna] = peca;
    } else {
        printf("Posição inválida!\n");
    }
}

int main() {
    char tabuleiro[TAMANHO][TAMANHO];

    // Inicializa o tabuleiro
    inicializarTabuleiro(tabuleiro);

    // Exemplo: Colocar algumas peças (simplificado)
    // 'P' = Peão, 'T' = Torre, 'C' = Cavalo, 'B' = Bispo, 'Q' = Rainha, 'K' = Rei
    // Letras minúsculas para peças pretas, maiúsculas para brancas

    // Coloca um Rei Branco na posição e1 (linha 7, coluna 4 no array)
    colocarPeca(tabuleiro, 7, 4, 'K');
    // Coloca uma Torre Preta na posição a8 (linha 0, coluna 0 no array)
    colocarPeca(tabuleiro, 0, 0, 't');
    // Coloca um Peão Branco na posição d2 (linha 6, coluna 3 no array)
    colocarPeca(tabuleiro, 6, 3, 'P');


    // Exibe o tabuleiro
    exibirTabuleiro(tabuleiro);

    printf("\nDesafio Xadrez Iniciante!\n");
    printf("Objetivo: Mover o Rei Branco (K) para uma casa segura (exemplo simples).\n");
    // Aqui você poderia adicionar lógica para verificar movimentos, etc.,
    // mas para um iniciante, exibir o tabuleiro e algumas peças já é um bom começo.

    return 0;
}
