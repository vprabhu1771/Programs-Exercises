# C

```c
#include<stdio.h>

int main()
{
	int num;

	printf("Enter any integer\n");

	scanf("%d", &num);

	if( (num%2) == 0 )
	{
		printf("%d is even\n", num);
	}
	else
	{
		printf("%d is odd\n", num);
	}

	return 0;
}
```

# CPP

```cpp
#include<iostream>

using namespace std;

int main()
{
	int num;

	cout << "Enter any integer" << endl;

	cin >> num;

	if( (num%2) == 0 )
	{		
		cout << num << " is even" << endl;
	}
	else
	{
		cout << num << " is odd" << endl;
	}

	return 0;
}
```
