# C
```c
#include<stdio.h>

#include<conio.h>

void main()
{
	char data

	clrscr();

	printf("Enter any character\n");

	scanf("%c", &data);

	printf("Character is %c\n", data);

	printf("ASCII is %d\n", data);

	getch();
}
```

# CPP

```cpp
#include <iostream>
#include <conio.h>  // For clrscr() and getch(), Turbo C++ specific

using namespace std;

int main() {
    char data;

    clrscr(); // Note: This works only in Turbo C++, not in modern compilers

    cout << "Enter any character: ";
    cin >> data;

    cout << "Character is: " << data << endl;
    cout << "ASCII is: " << static_cast<int>(data) << endl;

    getch(); // Pauses the output screen (Turbo C++ specific)
    return 0;
}
```
