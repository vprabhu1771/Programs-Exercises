```c
#include<stdio.h>
#include<conio.h>

void main()
{
	int num;

	clrscr();

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

	getch();
}
```