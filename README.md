# the_game_X-O.c
the_game_X&amp;O_uesd the progrmer c project 
#include <stdio.h>
#include <stdlib.h>

int main()
{
    char  x[3][3]={{'1','2','3'},
                 {'4','5','6',},
                  {'7','8','9'}};

    int plays =1,
        slot,
        row,
        column;
     printf(" by Ali Gamal Aziz  \n");
    printf("welcome to X - O game \n");
    printf("-----------------------\n\n");

    for (int i=0; i <3; i++){
        printf("      ");
        for (int j =0 ; j< 3; j++)
            printf("%c |", x[i][j]);
        printf("\n   --------------------\n" );
        }
        do {
        printf("\nplayer %d (%c) : " , plays % 2 != 0? 1 : 2,
                   plays % 2 != 0 ? 'x' : 'O' );
        scanf("%d", &slot);
        printf("\n");
        row = (slot -1 )/3;
        column = (slot -1) % 3;


          for (int i=0 ; i < 3 ; i++ ){
            printf("     ");
            for (int j=0; j < 3 ; j++){
                if (i == row && j == column)
                    x[i][j] =plays % 2 != 0? 'x' : 'O' ;

                printf("%c | ", x[i][j]);
            }
            printf("\n     -------------\n");
          }
          if (x[0][0] == x [1][1] && x[0][0] == x[2][2] ||
              x[2][0] == x [1][1] && x[2][0] == x[0][2] ){
                printf("\nplayer %d has won !! ", plays % 2 != 0? 1:2);
                return 0;
              }
          for (int i =0; i < 3; i++) {
            if (x[i][0] == x[i][1] &&  x[i][0] == x[i][2] ||
                x[0][i] == x[1][i] &&  x[0][i] == x[2][i]){
                    printf("\nplayer %d has won !!",plays %2 != 0? 1:2);
                    return 0;
                }
          }
         plays++;

        }while (plays <= 9);
        printf("\nGame has ended and no player has won ! \n");
        return 0;

}
