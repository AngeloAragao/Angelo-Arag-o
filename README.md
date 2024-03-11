# Angelo-Arag-o
#include <stdio.h>

void main(){
    int TAM = 52;
    int tempo[TAM];
    int tempoAux[TAM];
    int k, t;

    for(k=0;k<TAM;k++){
        tempo[k]=0;
        tempoAux[k]=0;
    }

    tempo[40] = 1;
    tempo[5] = 1;

    for(k=0;k<TAM;k++){
        if(tempo[k]==0)
           printf(" ");
        else
           printf("X");
    }
    printf("\n");
    for(t=1; t<=100; t++){

        for(k=0;k<TAM;k++){
            if(k==0)
                tempoAux[k] = (tempo[TAM-1] + tempo[k+1]) % 2;
            else if(k==TAM-1)
                tempoAux[k] = (tempo[k-1] + tempo[0]) % 2;
            else
                tempoAux[k] = (tempo[k-1] + tempo[k+1]) % 2;
        }
        for(k=0; k<TAM; k++){
            if(tempoAux[k]==0)
               printf(" ");
            else
               printf("X");
            tempo[k]=tempoAux[k];
            tempoAux[k]=0;
        }
        printf("\n");
    }



}
