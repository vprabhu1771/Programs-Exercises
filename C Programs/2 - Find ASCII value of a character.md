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

# Java 

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        char data;

        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter any character:");
        data = scanner.next().charAt(0);  // Read the first character of the input

        System.out.println("Character is: " + data);
        System.out.println("ASCII is: " + (int) data);  // Cast to int to get ASCII value

        scanner.close();
    }
}
```
