### Topic: Program to Find the Size of Arrays

Your C program calculates the memory occupied by arrays of different data types.

### Correct C Program

```c
#include <stdio.h>

int main()
{
    int data1[5];
    float data2[5];
    char data3[5];

    printf("Size of int array = %zu bytes\n", sizeof(data1));
    printf("Size of float array = %zu bytes\n", sizeof(data2));
    printf("Size of char array = %zu bytes\n", sizeof(data3));

    return 0;
}
```

### Output (Modern Systems)

```text
Size of int array = 20 bytes
Size of float array = 20 bytes
Size of char array = 5 bytes
```

Explanation:

* `int data1[5]` → 5 × 4 = 20 bytes
* `float data2[5]` → 5 × 4 = 20 bytes
* `char data3[5]` → 5 × 1 = 5 bytes

---

## C++

```cpp
#include <iostream>
using namespace std;

int main()
{
    int data1[5];
    float data2[5];
    char data3[5];

    cout << "Size of int array = " << sizeof(data1) << " bytes\n";
    cout << "Size of float array = " << sizeof(data2) << " bytes\n";
    cout << "Size of char array = " << sizeof(data3) << " bytes\n";

    return 0;
}
```

### Output

```text
Size of int array = 20 bytes
Size of float array = 20 bytes
Size of char array = 5 bytes
```

---

## Java

Java does not have a `sizeof` operator. You can calculate manually.

```java
public class Main {
    public static void main(String[] args) {

        int[] data1 = new int[5];
        float[] data2 = new float[5];
        char[] data3 = new char[5];

        System.out.println("Size of int array = " + (data1.length * Integer.BYTES) + " bytes");
        System.out.println("Size of float array = " + (data2.length * Float.BYTES) + " bytes");
        System.out.println("Size of char array = " + (data3.length * Character.BYTES) + " bytes");
    }
}
```

### Output

```text
Size of int array = 20 bytes
Size of float array = 20 bytes
Size of char array = 10 bytes
```

(`char` is 2 bytes in Java.)

---

## Python

```python
import sys

data1 = [0] * 5
data2 = [0.0] * 5
data3 = [''] * 5

print("Size of int array =", sys.getsizeof(data1), "bytes")
print("Size of float array =", sys.getsizeof(data2), "bytes")
print("Size of char array =", sys.getsizeof(data3), "bytes")
```

### Typical Output

```text
Size of int array = 96 bytes
Size of float array = 96 bytes
Size of char array = 96 bytes
```

Python lists store references to objects, so the reported size is the size of the list object itself, not simply the sum of element sizes.

### Summary

| Array Type | C/C++    | Java     | Python* |
| ---------- | -------- | -------- | ------- |
| `int[5]`   | 20 bytes | 20 bytes | Varies  |
| `float[5]` | 20 bytes | 20 bytes | Varies  |
| `char[5]`  | 5 bytes  | 10 bytes | Varies  |

*Python sizes depend on the interpreter and platform.
