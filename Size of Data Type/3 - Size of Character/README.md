### Topic: Size of Character Data Type

#### C Program

```c
#include <stdio.h>

int main()
{
    printf("Size of char = %zu bytes\n", sizeof(char));
    return 0;
}
```

**Output:**

```text
Size of char = 1 bytes
```

---

### C++

```cpp
#include <iostream>
using namespace std;

int main()
{
    cout << "Size of char = " << sizeof(char) << " bytes";
    return 0;
}
```

**Output:**

```text
Size of char = 1 bytes
```

---

### Java

Java `char` uses Unicode and occupies **2 bytes**.

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Size of char = " + Character.BYTES + " bytes");
    }
}
```

**Output:**

```text
Size of char = 2 bytes
```

---

### Python

Python does not have a separate `char` data type. A character is simply a string of length 1.

```python
import sys

ch = 'A'
print("Size of character =", sys.getsizeof(ch), "bytes")
```

**Typical Output:**

```text
Size of character = 50 bytes
```

(The exact size depends on the Python version and platform.)

### Summary

| Language | Type              | Size               |
| -------- | ----------------- | ------------------ |
| C        | `char`            | 1 byte             |
| C++      | `char`            | 1 byte             |
| Java     | `char`            | 2 bytes            |
| Python   | Character (`str`) | Typically 50 bytes |

**Topic Title:** *Program to Find the Size of Character Data Type*.
