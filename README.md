/*# biblioth-que-programme
 mini logiciel gestion bibliothèque  (pas encore termini )
 */
#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>

struct bibiliotheque{
       char name[50];
       char authur[50];
       float prix;
       int ISBN;
};

struct bibiliotheque b[50];

void addlivre(int i){

printf("entre le nome de livre :");
scanf("%s",b[i].name);
printf("entre le authure  de livre:");
scanf("%s",b[i].authur);
printf("entre le prix de livre :");
scanf("%f",&b[i].prix);
printf("entre le code ISBN  de livre :");
scanf("%d",&b[i].ISBN);

}

void recherchernom(int n){
  bool trouve=0;
  char nom[40];
  int i;
  printf("entre le nome de livre pour le rechercher:");
  scanf("%s",nom);
  for(i=0;i<n;i++){
    if(strcmp(b[i].name, nom) == 0){
           printf("le nome de livre est: %s\n", b[i].name);
           printf("le nome de authur est: %s\n", b[i].authur);
           printf("le prix de livre est: %.2f\n", b[i].prix);
           printf("le code ISBN de livre est: %d\n", b[i].ISBN);
        trouve=1;
    }
    }
    if (trouve==0){
    printf("aucun livre dans la bibloitheque avec se nom \n");
    }


}
void menu(){
    printf("1:ajouter un livre  a la bibliotheque \n");
    printf("2:rechercher un livre avec son nome \n");

    printf("3:quiter le programme \n");
}



int main()
{
    int n,i;
    int choix;
    printf("donner le nombre de livre neccicer :");
    scanf("%d",&n);
    do{
    menu();
    printf("entre votre choix:");
    scanf("%d",&choix);
    switch(choix){

               case 1:for(i=0;i<n;i++){
                       addlivre(i);
                       printf("\n");

                       }break;



               case 2:recherchernom(n);
                        break;

    }
    }while (choix!=3);
    return 0;
}
