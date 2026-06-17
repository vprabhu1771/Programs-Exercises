### Pattern Output (Input = E)

```text
A
AB
ABC
ABCD
ABCDE
```

---

## C Program

```c
#include <stdio.h>
#include <ctype.h>

int main()
{
    char input;

    printf("Enter the uppercase character you want to print in the last row: ");
    scanf(" %c", &input);

    input = toupper(input);

    for (int i = 1; i <= (input - 'A' + 1); i++)
    {
        char alphabet = 'A';

        for (int j = 1; j <= i; j++)
        {
            printf("%c", alphabet);
            alphabet++;
        }

        printf("\n");
    }

    return 0;
}
```

---

## C++ Program

```cpp
#include <iostream>
#include <cctype>

using namespace std;

int main()
{
    char input;

    cout << "Enter the uppercase character you want to print in the last row: ";
    cin >> input;

    input = toupper(input);

    for (int i = 1; i <= (input - 'A' + 1); i++)
    {
        char alphabet = 'A';

        for (int j = 1; j <= i; j++)
        {
            cout << alphabet;
            alphabet++;
        }

        cout << endl;
    }

    return 0;
}
```

---

## Java Program

```java
import java.util.Scanner;

public class App {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter the uppercase character you want to print in the last row: ");
        char input = sc.next().charAt(0);

        input = Character.toUpperCase(input);

        for (int i = 1; i <= (input - 'A' + 1); i++) {

            char alphabet = 'A';

            for (int j = 1; j <= i; j++) {
                System.out.print(alphabet);
                alphabet++;
            }

            System.out.println();
        }

        sc.close();
    }
}
```

---

## Python Program

```python
input_char = input("Enter the uppercase character you want to print in the last row: ").upper()

for i in range(1, ord(input_char) - ord('A') + 2):
    alphabet = 'A'

    for j in range(i):
        print(alphabet, end="")
        alphabet = chr(ord(alphabet) + 1)

    print()
```

### Sample Output

```text
Enter the uppercase character you want to print in the last row: E

A
AB
ABC
ABCD
ABCDE
```
