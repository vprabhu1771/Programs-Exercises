# c
```c
#include<stdio.h>
#include<stdlib.h>

int main()
{

    #ifdef _WIN32
        system('cls')
    #else
        system("clear");
    #endif

    int x[20][20], y[20][20], result[20][20], row, col, i, j;

    printf("enter row\n");

    scanf("%d", &row);


    printf("enter col\n");

    scanf("%d", &col);

    printf("Enter first matrix value\n");

    for(i = 0, i < row; i++)
    {
        for(j = 0, j < row; j++)
        {
            printf("row = %d : col = %d\n");

            scanf("%d", &x[i][j]);            
        }
    }

    printf("Enter second matrix value\n");

    for(i = 0, i < row; i++)
    {
        for(j = 0, j < row; j++)
        {
            printf("row = %d : col = %d\n");

            scanf("%d", &y[i][j]);            
        }
    }

    printf("Matrix Additon\n");

    for(i = 0, i < row; i++)
    {
        for(j = 0, j < row; j++)
        {
           result[i][j] = x[i][j] + y[i][j];
           
           printf("%d\t", result[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```