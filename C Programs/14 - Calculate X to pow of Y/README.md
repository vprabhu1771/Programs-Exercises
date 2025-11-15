```c
#include<stdio.h>
#include<conio.h>

void main()
{
    int base, exp;
    
    long long int value = 1;
    
    printf("Enter base number and exponent seperated by spaces..\n");
    scanf("%d%d", &base, &exp);
    
    while(exp!=0){
        value*=base;
        --exp;
    }
    printf("The answer is %lld", value);
    
    getch();
}
```