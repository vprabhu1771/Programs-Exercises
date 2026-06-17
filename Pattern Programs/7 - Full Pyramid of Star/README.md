This program prints a **full pyramid star pattern**.

### Output Example

For `rows = 5`:

```text
        *
      * * *
    * * * * *
  * * * * * * *
* * * * * * * * *
```

---

## C

```c
#include <stdio.h>

int main() {
    int i, space, rows, k = 0;

    printf("Enter the number of rows: ");
    scanf("%d", &rows);

    for(i = 1; i <= rows; ++i, k = 0) {

        for(space = 1; space <= rows - i; ++space) {
            printf("  ");
        }

        while(k != 2 * i - 1) {
            printf("* ");
            ++k;
        }

        printf("\n");
    }

    return 0;
}
```

---

## C++

```cpp
#include <iostream>
using namespace std;

int main() {
    int rows, k = 0;

    cout << "Enter the number of rows: ";
    cin >> rows;

    for(int i = 1; i <= rows; ++i, k = 0) {

        for(int space = 1; space <= rows - i; ++space) {
            cout << "  ";
        }

        while(k != 2 * i - 1) {
            cout << "* ";
            ++k;
        }

        cout << endl;
    }

    return 0;
}
```

---

## Java

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter the number of rows: ");
        int rows = sc.nextInt();

        int k = 0;

        for(int i = 1; i <= rows; ++i, k = 0) {

            for(int space = 1; space <= rows - i; ++space) {
                System.out.print("  ");
            }

            while(k != 2 * i - 1) {
                System.out.print("* ");
                ++k;
            }

            System.out.println();
        }

        sc.close();
    }
}
```

---

## Python

```python
rows = int(input("Enter the number of rows: "))

for i in range(1, rows + 1):
    k = 0

    for space in range(1, rows - i + 1):
        print("  ", end="")

    while k != 2 * i - 1:
        print("* ", end="")
        k += 1

    print()
```

### Topic

**Full Pyramid Star Pattern using Nested Loops**.

### Pattern Logic

* Outer loop controls the rows.
* First inner loop prints leading spaces.
* Second loop prints `2 × row - 1` stars.
* The number of stars increases by 2 in each row, forming a pyramid shape.
