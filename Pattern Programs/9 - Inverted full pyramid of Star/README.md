This program prints an **inverted full pyramid star pattern**.

### Output Example

For `rows = 5`:

```text
* * * * * * * * *
  * * * * * * *
    * * * * *
      * * *
        *
```

---

## C

```c
#include <stdio.h>

int main() {
    int rows, i, j, space;

    printf("Enter the number of rows: ");
    scanf("%d", &rows);

    for(i = rows; i >= 1; --i) {

        for(space = 0; space < rows - i; ++space)
            printf("  ");

        for(j = i; j <= 2 * i - 1; ++j)
            printf("* ");

        for(j = 0; j < i - 1; ++j)
            printf("* ");

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
    int rows;

    cout << "Enter the number of rows: ";
    cin >> rows;

    for(int i = rows; i >= 1; --i) {

        for(int space = 0; space < rows - i; ++space)
            cout << "  ";

        for(int j = i; j <= 2 * i - 1; ++j)
            cout << "* ";

        for(int j = 0; j < i - 1; ++j)
            cout << "* ";

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

        for(int i = rows; i >= 1; --i) {

            for(int space = 0; space < rows - i; ++space)
                System.out.print("  ");

            for(int j = i; j <= 2 * i - 1; ++j)
                System.out.print("* ");

            for(int j = 0; j < i - 1; ++j)
                System.out.print("* ");

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

for i in range(rows, 0, -1):

    for space in range(rows - i):
        print("  ", end="")

    for j in range(i, 2 * i):
        print("*", end=" ")

    for j in range(i - 1):
        print("*", end=" ")

    print()
```

### Topic

**Inverted Full Pyramid Star Pattern using Nested Loops**

### Pattern Logic

* The outer loop runs from `rows` down to `1`.
* The first inner loop prints leading spaces.
* The next two loops print `2 × i − 1` stars.
* The number of stars decreases by 2 in each row, forming an inverted pyramid.
