```c
#include<stdio.h>
#include<conio.h>

void main()
{
    int n, i;
    
    printf("Enter an integer to find multiplication table: ");
    scanf("%d", &n);
    
    for(i=1; i<=20;i++){
        printf("%d * %d = %d\n", n, i, n*i);
    }
    
    getch();
}
```