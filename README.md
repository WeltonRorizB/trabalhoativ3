# trabalhoativ3
#include<stdio.h>
#include<stdlib.h>
#include<algorithm>
#include<ctype.h>
using namespace std;

void menu(){
    printf("\n\t\t\t\t\t\t *******MENU*******\n");
    printf("\n\t\t\t\t\t\t A - GERAR VETOR\n");
    printf("\n\t\t\t\t\t\t B - ORDENAR VETOR\n");
    printf("\n\t\t\t\t\t\t C - BUSCA SEQUENCIAL\n");
    printf("\n\t\t\t\t\t\t D - BUSCA BINARIA\n");
    printf("\n\t\t\t\t\t\t E - SAIR\n");
}

int valoresAleatorios(int vetor[], int quantidadeNumero){

        printf("\t\t\t\t\t\t Informe o tamanho do vetor\n");
        scanf("%d",&quantidadeNumero);

        printf("\n\n\t\t\t\t\t\t\t Agora, informe os numeros contidos no vetor\n");
        for (int i = 0; i < quantidadeNumero; i++){
        scanf("%d",&vetor[quantidadeNumero]);
        }
            sort(vetor, vetor + quantidadeNumero);
            printf("%d", vetor[quantidadeNumero]);
            return(vetor[quantidadeNumero]);

}

int ordenarValores(int vetor[], int quantidadeNumero){
    for (int i = 0; i < quantidadeNumero; i++){
        printf("\t\t\t\t\t\t %d",&vetor[quantidadeNumero]);
    }
}

int buscaSequencial(int vetor[], int quantidadeNumero) {
     printf("\n\t\t\t\t\t\t Digite o valor da busca\n");
     int buscar;
    scanf("%d",&buscar);
    for (int i = 0; i < quantidadeNumero; i++) { // O(n)
        if (vetor[i] == buscar) {
            return i;
        }
    }
    return -1;
}

int buscaBinaria(int vetor[], int n) { // O(log n)
    int buscar;
    printf("\n\n\n\t\t\t Digite o valor da busca\n");
    scanf("%d",&buscar);
    int inicio = 0, fim = buscar - 1;
    while (inicio <= fim) {
        int meio = (inicio + fim) / 2;
        if (buscar == vetor[meio]) {
            return meio;
        } else if (buscar > vetor[meio]) {
            inicio = meio + 1;
        } else if (buscar < vetor[meio]) {
            fim = meio - 1;
        }
    }
}

int escolha(int vetor[],int quantidadeNumero){
char opcao;
    printf("\n\n\n\t\t\t\t\t\t Escolha uma letra para prosseguir\n");
    scanf("%c", &opcao);
    opcao = tolower(opcao);
    printf("\n\n\t\t\t Opcao escolhida: %c", opcao);
    for (int i = 0; i < quantidadeNumero; i++) {
        printf("%d ", vetor[i]);
    }

        switch (opcao){
             case 'a':
                        printf("\n\n\t\t\t\t\t\t Gerando valores aleatorios\n");
                        valoresAleatorios(vetor,quantidadeNumero);
                        opcao==0;
                        escolha(vetor,quantidadeNumero);

                            break;
             default:
                printf("\n____________________________________\n");
        }
        switch (opcao){


            case 'b':
                            printf("\n\n\t\t\t\t\t\t Ordenando vetores\n");
                            ordenarValores(vetor, quantidadeNumero);
                            escolha(vetor,quantidadeNumero);
                            break;


            case 'c':
                            printf("\n\n\t\t\t\t\t\t Busca sequencial\n");
                            buscaSequencial(vetor, quantidadeNumero);
                            escolha(vetor,quantidadeNumero);
                            break;


            case 'd':
                            printf("\n\n\t\t\t\t\t\t Busca binaria\n");
                            buscaBinaria(vetor,quantidadeNumero);
                            escolha(vetor,quantidadeNumero);
                            break;

            case 'e':
                            printf("\n\n\t\t\t\t\t\t Saindo do programa\n");

                            break;

            default:
            system("cls");
            printf("\n\t\t\t\t\t\t Inicie com a opc A para liberar as proximas opc\n");
                menu();
                escolha(vetor,quantidadeNumero);


                }

}


int main(){
    char opcao;
    int vetor[0],quantidadeNumero=0;

    menu();
    escolha(vetor,quantidadeNumero);

    return 0;
}
