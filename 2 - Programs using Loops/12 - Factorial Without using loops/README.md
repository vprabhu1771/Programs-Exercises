```c
#include<stdio.h>
#include<conio.h>
#include<math.h>

void main()
{
    int i, n, factorial;
    
    printf("Enter any number: ");
    scanf("%d",&n);
    
    factorial = 1;
    for(i=1; i<=n; i++){
        factorial = factorial * i;
        
    }
    printf("Factorial of %d is %d", n, factorial);
    
    getch();
}
```