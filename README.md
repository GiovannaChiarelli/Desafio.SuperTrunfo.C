#include <stdio.h>

int main() {
    // definindo variáveis
    int populacao1, pontosTuristicos1, populacao2, pontosTuristicos2;
    char estadoCarta1, estadoCarta2;
    float area1, pib1, area2, pib2;
    char codigoCarta1[4], nomeCidade1[50], codigoCarta2[4], nomeCidade2[50];

    // perguntas e leituras - carta 1
    printf("Digite o estado da carta 1 (letra de A a H): ");
    scanf(" %c", &estadoCarta1);

    printf("Digite o código da carta 1 (exemplo: A01): ");
    scanf(" %s", codigoCarta1);

    printf("Digite o nome da cidade da carta 1 (sem espaços): ");
    scanf(" %s", nomeCidade1);

    printf("Digite a população da cidade da carta 1: ");
    scanf(" %d", &populacao1);

    printf("Digite a área da cidade da carta 1: ");
    scanf(" %f", &area1);

    printf("Digite o PIB da cidade da carta 1: ");
    scanf(" %f", &pib1);

    printf("Digite o número de pontos turísticos da cidade da carta 1: ");
    scanf(" %d", &pontosTuristicos1);

    // perguntas e leituras - carta 2
    printf("Digite o estado da carta 2 (letra de A a H): ");
    scanf(" %c", &estadoCarta2);

    printf("Digite o código da carta 2 (exemplo: B03): ");
    scanf(" %s", codigoCarta2);

    printf("Digite o nome da cidade da carta 2 (sem espaços): ");
    scanf(" %s", nomeCidade2);

    printf("Digite a população da cidade da carta 2: ");
    scanf(" %d", &populacao2);

    printf("Digite a área da cidade da carta 2: ");
    scanf(" %f", &area2);

    printf("Digite o PIB da cidade da carta 2: ");
    scanf(" %f", &pib2);

    printf("Digite o número de pontos turísticos da cidade da carta 2: ");
    scanf(" %d", &pontosTuristicos2);

    return 0;
}
