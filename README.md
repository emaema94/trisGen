trisGen
=======
#include <stdlib.h>
#include <conio.h>
#define DIM 5

int trova(char mat[DIM][DIM]){
 int i;
 int j;
 int j2;
 for(i=0;i<DIM;i++){
 
                    for(j=0;j<DIM-1;j++){
                                        if((mat[i][j]!=mat[i][j+1])||(mat[i][j]!='X' && mat[i][j]!='O')){
                                                       
                                                      break; 
                                                      }                    
                    }
                    
                    if(j==DIM-1){
                                 return 1;
                                 } 
                               
                    for(j2=0;j2<DIM-1;j2++){
                                        if((mat[j2][i]!=mat[j2+1][i])||(mat[j2][i]!='X' && mat[j2][i]!='O'))
                                                      break;  
                                               
                    }
                    
                    if(j2==DIM-1){
                                 return 1;
                                 } 
                                 
                    
 }
 
      
 for(i=0;i<DIM-1;i++){
                      if(mat[i][i]!=mat[i+1][i+1]) break;
                                                   
                                                   
                      }
 if(i==DIM-1) return 1;
 
 for(i=0;i<DIM-1;i++){
                      if(mat[i][DIM-1-i]!=mat[i+1][DIM-2-i]) return 0;
                                                   
                                                   
                      }
 if(i==DIM-1) return 1;
 
 
 
     
    
    
    return 0;
    
}

void carica(char mat[DIM][DIM]){
    int i;
    int j;
    
    for(i=0;i<DIM;i++){
        for(j=0;j<DIM;j++){
                         printf("\nInserisci Campo %d,%d\n",i,j);
                         
                         mat[i][j]=getche();
                         
                         }   
        }
    
}

void visualizza(char mat[DIM][DIM]){
    int i;
    int j;
    
    for(i=0;i<DIM;i++){
        for(j=0;j<DIM;j++){
                         printf("[%c]",mat[i][j]);
                         
                         
                         }   
        printf("\n");
        }
    
}

int main(){
    char matr[DIM][DIM];
    
    printf("programma TRIS");
    carica(matr);
    visualizza(matr);
    
    if(trova(matr)==1)
                       printf("c'è il tris");
    else
        printf("non c'è il tris");
        
    getch();
    return 0;
    
       
    
    
}
