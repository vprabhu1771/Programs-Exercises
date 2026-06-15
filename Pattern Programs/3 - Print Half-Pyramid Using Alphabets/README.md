This program prints an **Alphabet Triangle Pattern** where each row contains the same alphabet.

### Output Example (Input: E)

```text
A
B B
C C C
D D D D
E E E E E
```

---

# C Program

```c
#include <stdio.h>
#include <ctype.h>

int main()
{
    char input, alphabet = 'A';

    printf("Enter the uppercase character you want to print in the last row: ");
    scanf(" %c", &input);

    input = toupper(input);

    for(int i = 1; i <= (input - 'A' + 1); i++)
    {
        for(int j = 1; j <= i; j++)
        {
            printf("%c ", alphabet);
        }

        alphabet++;
        printf("\n");
    }

    return 0;
}
```

---

# C++ Program

```cpp
#include <iostream>
#include <cctype>
using namespace std;

int main()
{
    char input, alphabet = 'A';

    cout << "Enter the uppercase character you want to print in the last row: ";
    cin >> input;

    input = toupper(input);

    for(int i = 1; i <= (input - 'A' + 1); i++)
    {
        for(int j = 1; j <= i; j++)
        {
            cout << alphabet << " ";
        }

        alphabet++;
        cout << endl;
    }

    return 0;
}
```

---

# Java Program

```java
import java.util.Scanner;

public class AlphabetPattern {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter the uppercase character you want to print in the last row: ");
        char input = sc.next().charAt(0);

        input = Character.toUpperCase(input);

        char alphabet = 'A';

        for(int i = 1; i <= (input - 'A' + 1); i++) {
            for(int j = 1; j <= i; j++) {
                System.out.print(alphabet + " ");
            }

            alphabet++;
            System.out.println();
        }

        sc.close();
    }
}
```

---

# Python Program

```python
input_char = input("Enter the uppercase character you want to print in the last row: ").upper()

alphabet = 'A'

for i in range(1, ord(input_char) - ord('A') + 2):
    for j in range(1, i + 1):
        print(alphabet, end=" ")
    alphabet = chr(ord(alphabet) + 1)
    print()
```

---

## Topic

**Alphabet Triangle Pattern Using Nested Loops**

### Concepts Used

* Nested loops
* Character manipulation
* ASCII/Unicode values
* Pattern printing
* User input

### Algorithm

1. Read a character from the user.
2. Convert it to uppercase.
3. Start with alphabet `'A'`.
4. For each row:

   * Print the current alphabet `i` times.
   * Move to the next alphabet.
5. Continue until the entered character is reached.
