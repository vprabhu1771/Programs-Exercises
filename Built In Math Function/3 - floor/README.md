# C
```c
#include<stdio.h>

#include<math.h>

int main()
{
	float data = 22.25;
	
	printf("floor value %d\n", floor(data));

	return 0;
}
```
```
OUTPUT

floor value 22.000000
```

## C++ – `floor()` Example

```cpp
#include <iostream>
#include <cmath>

using namespace std;

int main()
{
    float data = 22.25;

    cout << "floor value " << floor(data) << endl;

    return 0;
}
```

---

## Java – `Math.floor()` Example

```java
public class Main {
    public static void main(String[] args) {
        double data = 22.25;

        System.out.println("floor value " + Math.floor(data));
    }
}
```

---

## Python – `math.floor()` Example

```python
import math

data = 22.25

print("floor value", math.floor(data))
```

---

## Output

```text
floor value 22.000000   // C
floor value 22.0        // Java
floor value 22          // Python
```

---

## Equivalent Functions

| Language | Function       |
| -------- | -------------- |
| C        | `floor()`      |
| C++      | `floor()`      |
| Java     | `Math.floor()` |
| Python   | `math.floor()` |

### Example Results

| Input  | Floor Value |
| ------ | ----------- |
| 22.25  | 22          |
| 22.99  | 22          |
| 22.01  | 22          |
| -22.25 | -23         |

**Floor** returns the largest integer less than or equal to the given number.

Examples:

* `floor(22.25)` → `22`
* `floor(22.99)` → `22`
* `floor(-22.25)` → `-23`
