# C
```c
#include<stdio.h>

#include<math.h>

int main()
{
	float data = 25;
	
	printf("square root value %f\n", sqrt(data));

	return 0;
}
```
```
OUTPUT

square root value 5.000000
```

## C++

```cpp
#include <iostream>
#include <cmath>

using namespace std;

int main()
{
    float data = 25;

    cout << "square root value " << sqrt(data) << endl;

    return 0;
}
```

---

## Java

```java
public class Main {
    public static void main(String[] args) {
        double data = 25;

        System.out.println("square root value " + Math.sqrt(data));
    }
}
```

---

## Python

```python
import math

data = 25

print("square root value", math.sqrt(data))
```

---

## Output

```text
square root value 5.000000   // C
square root value 5.0        // Java
square root value 5.0        // Python
```

---

## Equivalent Functions

| Language | Function      |
| -------- | ------------- |
| C        | `sqrt()`      |
| C++      | `sqrt()`      |
| Java     | `Math.sqrt()` |
| Python   | `math.sqrt()` |

### Explanation

`sqrt()` calculates the square root of a number:

\sqrt{x}

For `data = 25`:

\sqrt{25}=5

### More Examples

| Input | Square Root |
| ----- | ----------- |
| 25    | 5           |
| 36    | 6           |
| 49    | 7           |
| 64    | 8           |
| 100   | 10          |

The square root of a number is the value that, when multiplied by itself, gives the original number. For example, `5 × 5 = 25`, so `√25 = 5`.
