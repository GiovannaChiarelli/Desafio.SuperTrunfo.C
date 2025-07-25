#include <stdio.h>

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

    int opcao;
    printf("\nEscolha o atributo para comparar:\n");
    printf("1 - População\n");
    printf("2 - Área\n");
    printf("3 - PIB\n");
    printf("4 - Pontos Turísticos\n");
    printf("5 - Densidade Demográfica\n");
    printf("Digite sua opção: ");
    scanf("%d", &opcao);

    printf("\nComparando %s e %s\n\n", nomeCidade1, nomeCidade2);

    switch(opcao) {
        case 1:
            printf("População:\n%s: %d\n%s: %d\n", nomeCidade1, populacao1, nomeCidade2, populacao2);
            if (populacao1 > populacao2)
                printf("\nVencedor: %s\n", nomeCidade1);
            else if (populacao2 > populacao1)
                printf("\nVencedor: %s\n", nomeCidade2);
            else
                printf("\nEmpate!\n");
            break;

        case 2:
            printf("Área:\n%s: %.2f\n%s: %.2f\n", nomeCidade1, area1, nomeCidade2, area2);
            if (area1 > area2)
                printf("\nVencedor: %s\n", nomeCidade1);
            else if (area2 > area1)
                printf("\nVencedor: %s\n", nomeCidade2);
            else
                printf("\nEmpate!\n");
            break;

        case 3:
            printf("PIB (em bilhões):\n%s: %.2f\n%s: %.2f\n", nomeCidade1, pib1, nomeCidade2, pib2);
            if (pib1 > pib2)
                printf("\nVencedor: %s\n", nomeCidade1);
            else if (pib2 > pib1)
                printf("\nVencedor: %s\n", nomeCidade2);
            else
                printf("\nEmpate!\n");
            break;

        case 4:
            printf("Pontos Turísticos:\n%s: %d\n%s: %d\n", nomeCidade1, pontosTuristicos1, nomeCidade2, pontosTuristicos2);
            if (pontosTuristicos1 > pontosTuristicos2)
                printf("\nVencedor: %s\n", nomeCidade1);
            else if (pontosTuristicos2 > pontosTuristicos1)
                printf("\nVencedor: %s\n", nomeCidade2);
            else
                printf("\nEmpate!\n");
            break;

        case 5:
            printf("Densidade Demográfica:\n%s: %.2f\n%s: %.2f\n", nomeCidade1, densidade1, nomeCidade2, densidade2);
            if (densidade1 < densidade2)
                printf("\nVencedor: %s\n", nomeCidade1);
            else if (densidade2 < densidade1)
                printf("\nVencedor: %s\n", nomeCidade2);
            else
                printf("\nEmpate!\n");
            break;

        default:
            printf("Opção inválida! Escolha entre 1 e 5.\n");
    }

    return 0;
}
