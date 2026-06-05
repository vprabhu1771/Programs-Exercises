```c
#include<stdio.h>

int main()
{
    int a, b;

    printf("Enter a\n");

    scanf("%d", &a);

    printf("Enter b\n");

    scanf("%d", &b);

     // Using ternary operator
    (a > b) ? printf("a = %d is Maximum\n", a)
            : printf("b = %d is Maximum\n", b);

    // OR

    if(a > b)
    {
        printf("a = %d is Maximum\n", a);
    }
    else
    {
        printf("b = %d is maximum\n", b);
    }
    
    return 0;
}
```
