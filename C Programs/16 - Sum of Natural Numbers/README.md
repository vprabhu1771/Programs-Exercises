```c
#include<stdio.h>
#include<conio.h>

void main()
{
    int n, count, sum = 0;
    
    printf("Enter an integer: ");
    scanf("%d", &n);
    
    count = 1;
    while( count <= n){
        sum += count;
        ++count;
    }
    printf("Sum = %d", sum);
    getch();
}
```