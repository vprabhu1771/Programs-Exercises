```
#include<stdio.h>

int main()
{
	float celsius, fahrenheit;

    printf("Enter Temperature in Fahrenheit: ");
    scanf("%f", &fahrenheit);

    // C = (F - 32) * 5/9;
    // C = (F - 32) * 1.8;    
    celsius = (fahrenheit - 32) * 5 / 9;

    printf("Temperature in celsius: %.2f\n", celsius);

    return 0;
}
```
