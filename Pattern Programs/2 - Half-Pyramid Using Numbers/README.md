This program prints a **number triangle pattern**.

### Output Example (rows = 5)

```text
1
1 2
1 2 3
1 2 3 4
1 2 3 4 5
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
            printf("%d ", j);
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
            cout << j << " ";
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

public class NumberPattern {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of rows: ");
        int rows = sc.nextInt();

        for(int i = 1; i <= rows; i++) {
            for(int j = 1; j <= i; j++) {
                System.out.print(j + " ");
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
        print(j, end=" ")
    print()
```

---

## Topic

**Number Triangle Pattern using Nested Loops**

### Concepts Used

* Nested `for` loops
* Pattern printing
* User input
* Loop control
* Number sequences

### Algorithm

1. Read the number of rows.
2. Use an outer loop for rows (`i = 1` to `rows`).
3. Use an inner loop for columns (`j = 1` to `i`).
4. Print the value of `j`.
5. Move to the next line after each row.
6. Stop when all rows are printed.
