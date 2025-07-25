#include <stdio.h>
#include <string.h>

int main() {
    int populacao1, pontosTuristicos1, populacao2, pontosTuristicos2;
    char estadoCarta1, estadoCarta2;
    float area1, pib1, area2, pib2;
    char codigoCarta1[4], nomeCidade1[50], codigoCarta2[4], nomeCidade2[50];

    float densidade1, densidade2;

    printf("Digite o estado da carta 1 (letra de A a H): ");
    scanf(" %c", &estadoCarta1);
    printf("Digite o código da carta 1 (exemplo: A01): ");
    scanf(" %s", codigoCarta1);
    printf("Digite o nome da cidade da carta 1 (sem espaços): ");
    scanf(" %s", nomeCidade1);
    printf("Digite a população da cidade da carta 1: ");
    scanf("%d", &populacao1);
    printf("Digite a área da cidade da carta 1: ");
    scanf("%f", &area1);
    printf("Digite o PIB da cidade da carta 1 (em bilhões): ");
    scanf("%f", &pib1);
    printf("Digite o número de pontos turísticos da cidade da carta 1: ");
    scanf("%d", &pontosTuristicos1);

    printf("Digite o estado da carta 2 (letra de A a H): ");
    scanf(" %c", &estadoCarta2);
    printf("Digite o código da carta 2 (exemplo: B03): ");
    scanf(" %s", codigoCarta2);
    printf("Digite o nome da cidade da carta 2 (sem espaços): ");
    scanf(" %s", nomeCidade2);
    printf("Digite a população da cidade da carta 2: ");
    scanf("%d", &populacao2);
    printf("Digite a área da cidade da carta 2: ");
    scanf("%f", &area2);
    printf("Digite o PIB da cidade da carta 2 (em bilhões): ");
    scanf("%f", &pib2);
    printf("Digite o número de pontos turísticos da cidade da carta 2: ");
    scanf("%d", &pontosTuristicos2);

    densidade1 = populacao1 / area1;
    densidade2 = populacao2 / area2;

    int opcao1, opcao2;
    int valido;

    void mostrarMenu(int ignorar) {
        printf("\nEscolha um atributo para comparar:\n");
        if (ignorar != 1) printf("1 - População\n");
        if (ignorar != 2) printf("2 - Área\n");
        if (ignorar != 3) printf("3 - PIB\n");
        if (ignorar != 4) printf("4 - Pontos Turísticos\n");
        if (ignorar != 5) printf("5 - Densidade Demográfica\n");
        printf("Digite sua opção: ");
    }

    do {
        mostrarMenu(0);
        scanf("%d", &opcao1);
        valido = (opcao1 >= 1 && opcao1 <= 5);
        if (!valido) printf("Opção inválida! Tente novamente.\n");
    } while (!valido);

    do {
        mostrarMenu(opcao1);
        scanf("%d", &opcao2);
        valido = (opcao2 >= 1 && opcao2 <= 5 && opcao2 != opcao1);
        if (!valido) printf("Opção inválida ou repetida! Tente novamente.\n");
    } while (!valido);

    char nomeAtributo1[30], nomeAtributo2[30];
    float valor1_atr1, valor2_atr1, valor1_atr2, valor2_atr2;

    switch(opcao1) {
        case 1:
            strcpy(nomeAtributo1, "População");
            valor1_atr1 = populacao1;
            valor2_atr1 = populacao2;
            break;
        case 2:
            strcpy(nomeAtributo1, "Área");
            valor1_atr1 = area1;
            valor2_atr1 = area2;
            break;
        case 3:
            strcpy(nomeAtributo1, "PIB");
            valor1_atr1 = pib1;
            valor2_atr1 = pib2;
            break;
        case 4:
            strcpy(nomeAtributo1, "Pontos Turísticos");
            valor1_atr1 = pontosTuristicos1;
            valor2_atr1 = pontosTuristicos2;
            break;
        case 5:
            strcpy(nomeAtributo1, "Densidade Demográfica");
            valor1_atr1 = densidade1;
            valor2_atr1 = densidade2;
            break;
    }

    switch(opcao2) {
        case 1:
            strcpy(nomeAtributo2, "População");
            valor1_atr2 = populacao1;
            valor2_atr2 = populacao2;
            break;
        case 2:
            strcpy(nomeAtributo2, "Área");
            valor1_atr2 = area1;
            valor2_atr2 = area2;
            break;
        case 3:
            strcpy(nomeAtributo2, "PIB");
            valor1_atr2 = pib1;
            valor2_atr2 = pib2;
            break;
        case 4:
            strcpy(nomeAtributo2, "Pontos Turísticos");
            valor1_atr2 = pontosTuristicos1;
            valor2_atr2 = pontosTuristicos2;
            break;
        case 5:
            strcpy(nomeAtributo2, "Densidade Demográfica");
            valor1_atr2 = densidade1;
            valor2_atr2 = densidade2;
            break;
    }

    int vencedorAtributo(float v1, float v2, int atributo) {
        return (atributo == 5) ? (v1 < v2 ? 1 : (v2 < v1 ? 2 : 0))
                               : (v1 > v2 ? 1 : (v2 > v1 ? 2 : 0));
    }

    int vencedor1 = vencedorAtributo(valor1_atr1, valor2_atr1, opcao1);
    int vencedor2 = vencedorAtributo(valor1_atr2, valor2_atr2, opcao2);

    float soma1 = valor1_atr1 + valor1_atr2;
    float soma2 = valor2_atr1 + valor2_atr2;

    printf("\nComparação entre %s e %s\n\n", nomeCidade1, nomeCidade2);
    printf("%s:\n  %s: %.2f\n  %s: %.2f\n\n", nomeCidade1, nomeAtributo1, valor1_atr1, nomeAtributo2, valor1_atr2);
    printf("%s:\n  %s: %.2f\n  %s: %.2f\n\n", nomeCidade2, nomeAtributo1, valor2_atr1, nomeAtributo2, valor2_atr2);

    printf("Soma dos atributos:\n%s: %.2f\n%s: %.2f\n\n", nomeCidade1, soma1, nomeCidade2, soma2);

    if (soma1 > soma2)
        printf("Vencedor da rodada: %s\n", nomeCidade1);
    else if (soma2 > soma1)
        printf("Vencedor da rodada: %s\n", nomeCidade2);
    else
        printf("Empate!\n");

    return 0;
}
