This program prints a **palindromic number pyramid pattern**.

### Output Example

For `rows = 5`:

```text
        1
      2 3 2
    3 4 5 4 3
  4 5 6 7 6 5 4
5 6 7 8 9 8 7 6 5
```

---

## C

```c
#include <stdio.h>

int main() {
    int i, space, rows, k = 0, count = 0, count1 = 0;

    printf("Enter the number of rows: ");
    scanf("%d", &rows);

    for(i = 1; i <= rows; ++i) {

        for(space = 1; space <= rows - i; ++space) {
            printf("  ");
            ++count;
        }

        while(k != 2 * i - 1) {
            if(count <= rows - 1) {
                printf("%d ", i + k);
                ++count;
            } else {
                ++count1;
                printf("%d ", (i + k - 2 * count1));
            }
            ++k;
        }

        count1 = count = k = 0;
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
    int rows, k = 0, count = 0, count1 = 0;

    cout << "Enter the number of rows: ";
    cin >> rows;

    for(int i = 1; i <= rows; ++i) {

        for(int space = 1; space <= rows - i; ++space) {
            cout << "  ";
            ++count;
        }

        while(k != 2 * i - 1) {
            if(count <= rows - 1) {
                cout << i + k << " ";
                ++count;
            } else {
                ++count1;
                cout << (i + k - 2 * count1) << " ";
            }
            ++k;
        }

        count1 = count = k = 0;
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

        int k = 0, count = 0, count1 = 0;

        for(int i = 1; i <= rows; ++i) {

            for(int space = 1; space <= rows - i; ++space) {
                System.out.print("  ");
                ++count;
            }

            while(k != 2 * i - 1) {
                if(count <= rows - 1) {
                    System.out.print((i + k) + " ");
                    ++count;
                } else {
                    ++count1;
                    System.out.print((i + k - 2 * count1) + " ");
                }
                ++k;
            }

            count1 = count = k = 0;
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
    count = 0
    count1 = 0

    for space in range(1, rows - i + 1):
        print("  ", end="")
        count += 1

    while k != 2 * i - 1:
        if count <= rows - 1:
            print(i + k, end=" ")
            count += 1
        else:
            count1 += 1
            print(i + k - 2 * count1, end=" ")
        k += 1

    print()
```

### Topic

**Palindromic Number Pyramid Pattern using Nested Loops**

### Pattern Logic

1. Print leading spaces to center the pyramid.
2. Print numbers in ascending order from the row number.
3. After reaching the middle, print numbers in descending order.
4. Each row forms a palindrome, creating a symmetric number pyramid.
