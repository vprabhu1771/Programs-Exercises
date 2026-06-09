# C
```c
#include<stdio.h>

#include<string.h>

#define size 100

int main()
{
	char str1[size], str2[size];	

	puts("Enter your name");

	scanf("%s", str1);
		
	// string copy function first argument is destination
	// second argument is source
	strcpy(str2, str1);

	puts("copyed string");

	printf("%s\n", str2);

	return 0;
}
```
```
OUTPUT

Enter your name
prabhu

prabhu
```
