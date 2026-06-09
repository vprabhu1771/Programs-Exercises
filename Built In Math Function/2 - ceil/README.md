# C
```c
#include<stdio.h>

#include<math.h>

int main()
{
	float data = 22.25;
	
	printf("ceil value %f\n", ceil(data));

	return 0;
}
```
```
OUTPUT

ceil value 23.000000
```

## C++

```cpp
#include <iostream>
#include <cmath>

using namespace std;

int main()
{
    float data = 22.25;

    cout << "ceil value " << ceil(data) << endl;

    return 0;
}
```

---

## Java

```java
public class Main {
    public static void main(String[] args) {
        double data = 22.25;

        System.out.println("ceil value " + Math.ceil(data));
    }
}
```

---

## Python

```python
import math

data = 22.25

print("ceil value", math.ceil(data))
```

---

## Output

```text
ceil value 23.000000   // C
ceil value 23.0        // Java
ceil value 23          // Python
```

---

## Equivalent Functions

| Language | Function      |
| -------- | ------------- |
| C        | `ceil()`      |
| C++      | `ceil()`      |
| Java     | `Math.ceil()` |
| Python   | `math.ceil()` |

### Example Results

| Input  | Ceil Value |
| ------ | ---------- |
| 22.25  | 23         |
| 22.99  | 23         |
| 22.01  | 23         |
| -22.25 | -22        |

**Ceiling (ceil)** returns the smallest integer greater than or equal to the given number. For `22.25`, the result is `23`.
