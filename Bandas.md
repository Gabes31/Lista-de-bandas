# Lista-de-bandas
Cria uma lista com bandas digitadas pelo usuário.
#include <stdio.h>
#include <string.h>

typedef struct{
    char nome[20]; 
    char estilo[20];
    int qntInteg;
    int rank;
}BANDA;


void lerBanda(BANDA *v, int qnt){
    
    
    for(int i = 0; i < qnt; i++){
        printf("\nDigite o nome: ");        scanf("%s",v[i].nome);
        printf("Digite o estilo: ");        scanf("%s",v[i].estilo);
        printf("Digite o integrantes: ");   scanf("%d",&v[i].qntInteg);
        printf("Digite o seu rank: ");      scanf("%d",&v[i].rank);
    }
    
}

void listarBandas(BANDA *v, int qnt){
    
    
    printf("As bandas sao: ");
    for(int i = 0; i < qnt; i++){
        printf("\nNome da Banda: %s", v[i].nome); 
        printf("\nEstilo da Banda: %s", v[i].estilo); 
        printf("\nQuantidade de integrantes da Banda: %d", v[i].qntInteg); 
        printf("\nRank da Banda: %d\n", v[i].rank); 
        
    }
}

void buscarNome(BANDA *v, int qnt, char *aux) {
    int result = 0;
    printf("\nDigite o nome da Banda para pesquisa: \n");
    scanf("%s", aux);
    for (int i = 0; i < qnt; i++) {
        if (strcmp(v[i].nome, aux) == 0) {
            result = 1;
            printf("Resultados: ");
            printf("\nNome da Banda: %s", v[i].nome);
            printf("\nEstilo da Banda: %s", v[i].estilo);
            printf("\nQuantidade de integrantes da Banda: %d", v[i].qntInteg);
            printf("\nRank da Banda: %d\n", v[i].rank);
        }
    }
}

void buscarRank(BANDA *v, int qnt){
    int rankDigit;
    
    printf("\nQual Rank voce deseja?\n");
    scanf("%d",&rankDigit);
    
    for(int i = 0; i < qnt; i++){
        if(rankDigit == v[i].rank){
            printf("A banda é:");
            printf("\nNome da Banda: %s", v[i].nome); 
            printf("\nEstilo da Banda: %s", v[i].estilo); 
            printf("\nQuantidade de integrantes da Banda: %d", v[i].qntInteg); 
            printf("\nRank da Banda: %d", v[i].rank);
            
        }
    }
    
}

void menu(){
    int qnt, opc = 0;
    BANDA v[10];
    char aux[50];
    
    printf("Digite a quantidade de bandas: \n");
    scanf("%d",&qnt);
    
    printf("\n------------MENU----------------\n");
    printf("\nOpcoes:");
    printf("\n1. Digitar as Bandas.");
    printf("\n2. Listar Todas as Bandas.");
    printf("\n3. Buscar por Nome.");
    printf("\n4. Buscar por Rank.");
    printf("\n5. Sair.");
    
   
    while(opc != 5){
        printf("\n\nDigite uma opcao entre 1 e 5.\n");
        scanf("%d",&opc);
        
        if(opc == 1){
            lerBanda(v, qnt);
        }
        if(opc == 2){
            listarBandas(v, qnt);
        }
        if(opc == 3){
            buscarNome(v, qnt, aux);
        }
        if(opc == 4){
            buscarRank(v, qnt);
        }
        if(opc > 5 || opc < 0){
        printf("Digite novamente\n");
        }
    }
    
    
}
void main(){
    menu();
    
}
