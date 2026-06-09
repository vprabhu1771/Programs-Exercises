### Topic: Size of Float Data Type

#### C Program

```c
#include <stdio.h>

int main()
{
    printf("Size of float = %zu bytes\n", sizeof(float));
    return 0;
}
```

**Output:**

```text
Size of float = 4 bytes
```

---

### C++

```cpp
#include <iostream>
using namespace std;

int main()
{
    cout << "Size of float = " << sizeof(float) << " bytes";
    return 0;
}
```

**Output:**

```text
Size of float = 4 bytes
```

---

### Java

Java's `float` is always 32-bit (4 bytes).

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Size of float = " + Float.BYTES + " bytes");
    }
}
```

**Output:**

```text
Size of float = 4 bytes
```

---

### Python

Python does not have a separate `float` data type like C/Java. Python's `float` is typically a 64-bit double-precision floating-point number.

```python
import sys

num = 1.0
print("Size of float =", sys.getsizeof(num), "bytes")
```

**Typical Output:**

```text
Size of float = 24 bytes
```

(The exact value may vary by Python version and platform.)

### Summary

| Language | Type           | Size               |
| -------- | -------------- | ------------------ |
| C        | `float`        | 4 bytes            |
| C++      | `float`        | 4 bytes            |
| Java     | `float`        | 4 bytes            |
| Python   | `float` object | Typically 24 bytes |

**Topic Title:** *Program to Find the Size of Float Data Type*.
