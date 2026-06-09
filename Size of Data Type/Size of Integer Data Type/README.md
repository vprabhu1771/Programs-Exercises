Your C program:

```c
#include<stdio.h>
#include<conio.h>

void main()
{
    clrscr();

    printf("size of integer = %d bytes\n", sizeof(int));

    getch();
}
```

prints:

```text
size of integer = 2 bytes
```

on old Turbo C compilers because `int` was **2 bytes (16-bit)**.

### Modern C/C++

On most modern systems:

```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Size of int = " << sizeof(int) << " bytes";
    return 0;
}
```

**Output (typically):**

```text
Size of int = 4 bytes
```

---

### Java

Java's `int` size is always **4 bytes (32 bits)**.

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Size of int = " + Integer.BYTES + " bytes");
    }
}
```

**Output:**

```text
Size of int = 4 bytes
```

---

### Python

Python integers are objects and have variable size.

```python
import sys

num = 0
print("Size of integer =", sys.getsizeof(num), "bytes")
```

**Output (may vary by version/platform):**

```text
Size of integer = 28 bytes
```

or

```text
Size of integer = 24 bytes
```

Unlike C/C++ and Java, Python integers grow automatically to store very large numbers.

### Comparison

| Language | Integer Type | Typical Size                         |
| -------- | ------------ | ------------------------------------ |
| Turbo C  | `int`        | 2 bytes                              |
| Modern C | `int`        | 4 bytes                              |
| C++      | `int`        | 4 bytes                              |
| Java     | `int`        | 4 bytes (fixed)                      |
| Python   | `int`        | Variable (about 24–28 bytes minimum) |

**Note:** `sizeof(int)` in modern C/C++ usually returns **4 bytes**, while the **2-byte output** comes from older 16-bit compilers such as **Turbo C**.
