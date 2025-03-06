#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Definição da estrutura Veiculo
typedef struct {
    char marca[20];
    char modelo[20];
    char cor[20];
    int ano_modelo;
    int ano_fabricacao;
    char combustivel[10];
    char placa[10];
} Veiculo;

int main() {
    Veiculo veiculos[5];
    char placa_busca[10];
    int i, encontrado = 0, opcao;

    do {
        printf("\nMenu:\n");
        printf("1 - Cadastrar veículos\n");
        printf("2 - Buscar veículo por placa\n");
        printf("3 - Sair\n");
        printf("Escolha uma opção: ");
        scanf("%d", &opcao);

        switch (opcao) {
            case 1:
                printf("Cadastro de 5 veículos:\n");
                for(i = 0; i < 5; i++) {
                    printf("\nVeículo %d:\n", i + 1);
                    printf("Marca: ");
                    scanf("%s", veiculos[i].marca);
                    printf("Modelo: ");
                    scanf("%s", veiculos[i].modelo);
                    printf("Cor: ");
                    scanf("%s", veiculos[i].cor);
                    printf("Ano do modelo: ");
                    scanf("%d", &veiculos[i].ano_modelo);
                    printf("Ano de fabricação: ");
                    scanf("%d", &veiculos[i].ano_fabricacao);
                    printf("Combustível (gasolina, etanol, flex, eletrico, hibrido): ");
                    scanf("%s", veiculos[i].combustivel);
                    printf("Placa: ");
                    scanf("%s", veiculos[i].placa);
                }
                break;
            case 2:
                printf("\nInforme a placa do veículo para busca: ");
                scanf("%s", placa_busca);
                encontrado = 0;
                for(i = 0; i < 5; i++) {
                    if(strcmp(veiculos[i].placa, placa_busca) == 0) {
                        printf("\nVeículo encontrado:\n");
                        printf("Marca: %s\n", veiculos[i].marca);
                        printf("Modelo: %s\n", veiculos[i].modelo);
                        printf("Cor: %s\n", veiculos[i].cor);
                        printf("Ano do modelo: %d\n", veiculos[i].ano_modelo);
                        printf("Ano de fabricação: %d\n", veiculos[i].ano_fabricacao);
                        printf("Combustível: %s\n", veiculos[i].combustivel);
                        printf("Placa: %s\n", veiculos[i].placa);
                        encontrado = 1;
                        break;
                    }
                }
                if (!encontrado) {
                    printf("Veículo não localizado.\n");
                }
                break;
            case 3:
                printf("Saindo...\n");
                break;
            default:
                printf("Opção inválida! Tente novamente.\n");
        }
    } while (opcao != 3);

    system("pause");
    return 0;
}
# localizar-carro
