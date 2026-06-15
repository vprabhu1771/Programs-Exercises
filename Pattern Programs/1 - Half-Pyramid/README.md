Your C++ program prints a **right-angled triangle star pattern**.

### Output Example (rows = 5)

```
*
* *
* * *
* * * *
* * * * *
```

---

# C Program

```c
#include <stdio.h>

int main()
{
    int rows;

    printf("Enter number of rows: ");
    scanf("%d", &rows);

    for(int i = 1; i <= rows; i++)
    {
        for(int j = 1; j <= i; j++)
        {
            printf("* ");
        }
        printf("\n");
    }

    return 0;
}
```

---

# C++ Program

```cpp
#include <iostream>
using namespace std;

int main()
{
    int rows;

    cout << "Enter number of rows: ";
    cin >> rows;

    for(int i = 1; i <= rows; i++)
    {
        for(int j = 1; j <= i; j++)
        {
            cout << "* ";
        }
        cout << endl;
    }

    return 0;
}
```

---

# Java Program

```java
import java.util.Scanner;

public class StarPattern {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of rows: ");
        int rows = sc.nextInt();

        for(int i = 1; i <= rows; i++) {
            for(int j = 1; j <= i; j++) {
                System.out.print("* ");
            }
            System.out.println();
        }

        sc.close();
    }
}
```

---

# Python Program

```python
rows = int(input("Enter number of rows: "))

for i in range(1, rows + 1):
    for j in range(1, i + 1):
        print("*", end=" ")
    print()
```

---

### Topic

**Star Pattern Program using Nested Loops (Right-Angled Triangle Pattern)**

**Concepts Used:**

* `for` loops
* Nested loops
* Pattern printing
* User input
* Iteration control based on row number
