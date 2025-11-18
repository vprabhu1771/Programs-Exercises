```c
#include<stdio.h>
#include<conio.h>

void main()
{
    float num;
    
    printf("Enter any number: ");
    scanf("%f",&num);
    
    if(num == 0){
        printf("%.2f is either positive nor negative", num);
    }
    else if(num > 0){
        printf("%.2f is positive",num);
    }
    else{
        printf("%.2f is negative", num);
    }
    
    getch();    
}
```