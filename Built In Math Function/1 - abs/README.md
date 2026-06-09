# C
```c
#include<stdio.h>

#include<math.h>

int main()
{
	int data = -22;
	
	printf("absolute value %d\n", abs(data));

	return 0;
}
```
```
OUTPUT

absolute value 22
```

## Absolute Value Program

### C++

```cpp
#include <iostream>
#include <cmath>

using namespace std;

int main()
{
    int data = -22;

    cout << "absolute value " << abs(data) << endl;

    return 0;
}
```

---

### Java

```java
public class Main {
    public static void main(String[] args) {
        int data = -22;

        System.out.println("absolute value " + Math.abs(data));
    }
}
```

---

### Python

```python
data = -22

print("absolute value", abs(data))
```

---

### Output

```text
absolute value 22
```

### Equivalent Functions

| Language | Absolute Value Function |
| -------- | ----------------------- |
| C        | `abs()`                 |
| C++      | `abs()`                 |
| Java     | `Math.abs()`            |
| Python   | `abs()`                 |

### Notes

* `abs()` returns the positive value of a number.
* It works with negative, positive, and zero values.
* For floating-point numbers:

  * C/C++: `fabs()`
  * Java: `Math.abs()`
  * Python: `abs()`

Example:

```text
abs(-22) = 22
abs(22)  = 22
abs(0)   = 0
```
