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

Here’s the equivalent Python version of your C program:

```python
# Fahrenheit to Celsius conversion

fahrenheit = float(input("Enter Temperature in Fahrenheit: "))

# C = (F - 32) * 5/9
celsius = (fahrenheit - 32) * 5 / 9

print("Temperature in Celsius: {:.2f}".format(celsius))
```

If you want a shorter version using f-strings (modern Python):

```python
fahrenheit = float(input("Enter Temperature in Fahrenheit: "))
celsius = (fahrenheit - 32) * 5 / 9
print(f"Temperature in Celsius: {celsius:.2f}")
```
