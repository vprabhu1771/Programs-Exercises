```c
#include<stdio.h>

void main()
{
	float a, b, temp;

	printf("Enter a value\n");

	scanf("%f", &a);

	printf("Enter b value\n");

	scanf("%f", &b);

	temp = a;

	a = b;

	b = temp;

	printf("a = %f\n", a);	

	printf("b = %f\n", b);
}
```

```cpp
#include<iostream>

using namespace std;

void main()
{
	float a, b, temp;

	cout << "Enter a value" << endl;

	cin >> a;

	cout << "Enter b value" << endl;

	cin >> b;

	temp = a;

	a = b;

	b = temp;

	cout << "a = " << a << endl;

	cout << "b = " << b << endl;
}
```
