Your C program prints an **inverted right-angled star pattern**.

### Output Example

For `rows = 5`:

```text
* * * * *
* * * *
* * *
* *
*
```

## C

```c
#include <stdio.h>

int main() {
    int i, j, rows;

    printf("Enter the number of rows: ");
    scanf("%d", &rows);

    for(i = rows; i >= 1; --i) {
        for(j = 1; j <= i; ++j) {
            printf("* ");
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
    int rows;

    cout << "Enter the number of rows: ";
    cin >> rows;

    for(int i = rows; i >= 1; --i) {
        for(int j = 1; j <= i; ++j) {
            cout << "* ";
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

        for(int i = rows; i >= 1; --i) {
            for(int j = 1; j <= i; ++j) {
                System.out.print("* ");
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

for i in range(rows, 0, -1):
    for j in range(i):
        print("*", end=" ")
    print()
```

### Topic

**Inverted Right-Angled Triangle Star Pattern using Nested Loops**.
