#include <stdio.h>

int main() {
    // Dados da Carta 1 - São Paulo
    char estado1[] = "SP";
    char codigo1[] = "SP1";
    char nomeCidade1[] = "São Paulo";
    int populacao1 = 12300000;
    float area1 = 1521.11;
    float pib1 = 2300.0; // PIB em bilhões de reais
    int pontosTuristicos1 = 15;

    // Dados da Carta 2 - Rio de Janeiro
    char estado2[] = "RJ";
    char codigo2[] = "RJ1";
    char nomeCidade2[] = "Rio de Janeiro";
    int populacao2 = 6700000;
    float area2 = 1182.3;
    float pib2 = 410.0; // PIB em bilhões de reais
    int pontosTuristicos2 = 12;

    // Cálculo da densidade populacional
    float densidade1 = populacao1 / area1;
    float densidade2 = populacao2 / area2;

    // Cálculo do PIB per capita
    // Convertendo PIB de bilhões para reais antes de dividir
    float pibPerCapita1 = (pib1 * 1000000000) / populacao1;
    float pibPerCapita2 = (pib2 * 1000000000) / populacao2;

    // Exibição das informações das cartas
    printf("=== CARTA 1 ===\n");
    printf("Cidade: %s (%s)\n", nomeCidade1, estado1);
    printf("População: %d\n", populacao1);
    printf("Área: %.2f km²\n", area1);
    printf("PIB: R$ %.2f bilhões\n", pib1);
    printf("Pontos turísticos: %d\n", pontosTuristicos1);
    printf("Densidade Populacional: %.2f hab/km²\n", densidade1);
    printf("PIB per capita: R$ %.2f\n\n", pibPerCapita1);

    printf("=== CARTA 2 ===\n");
    printf("Cidade: %s (%s)\n", nomeCidade2, estado2);
    printf("População: %d\n", populacao2);
    printf("Área: %.2f km²\n", area2);
    printf("PIB: R$ %.2f bilhões\n", pib2);
    printf("Pontos turísticos: %d\n", pontosTuristicos2);
    printf("Densidade Populacional: %.2f hab/km²\n", densidade2);
    printf("PIB per capita: R$ %.2f\n\n", pibPerCapita2);

    // Comparação de atributo (fixo: População)
    printf("=== COMPARAÇÃO DE CARTAS (Atributo: População) ===\n");

    if (populacao1 > populacao2) {
        printf("Resultado: Carta 1 (%s) venceu com %d habitantes!\n", nomeCidade1, populacao1);
    } else if (populacao2 > populacao1) {
        printf("Resultado: Carta 2 (%s) venceu com %d habitantes!\n", nomeCidade2, populacao2);
    } else {
        printf("Resultado: Empate! Ambas as cidades têm a mesma população.\n");
    }

    return 0;
}
