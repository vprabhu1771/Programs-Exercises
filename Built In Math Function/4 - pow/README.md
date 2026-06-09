# C
```c
#include<stdio.h>

#include<math.h>

int main()
{
	int x = 2, y = 3;
	
	printf("raised power value %f\n", pow(x,y));

	return 0;
}

OUTPUT

raised power value 8.000000
```
## C++

```cpp
#include <iostream>
#include <cmath>

using namespace std;

int main()
{
    int x = 2, y = 3;

    cout << "raised power value " << pow(x, y) << endl;

    return 0;
}
```

---

## Java

```java
public class Main {
    public static void main(String[] args) {
        int x = 2, y = 3;

        System.out.println("raised power value " + Math.pow(x, y));
    }
}
```

---

## Python

```python
x = 2
y = 3

print("raised power value", pow(x, y))
```

---

## Output

```text
raised power value 8.000000   // C
raised power value 8.0        // Java
raised power value 8          // Python
```

---

## Equivalent Functions

| Language | Function         |
| -------- | ---------------- |
| C        | `pow(x, y)`      |
| C++      | `pow(x, y)`      |
| Java     | `Math.pow(x, y)` |
| Python   | `pow(x, y)`      |

### Example Results

| x  | y | Result |
| -- | - | ------ |
| 2  | 3 | 8      |
| 5  | 2 | 25     |
| 10 | 3 | 1000   |
| 4  | 0 | 1      |

### Explanation

`pow(x, y)` calculates:

x^y

For `x = 2` and `y = 3`:

2^3 = 8

So the output is:

```text
raised power value 8
```
