# C
```c
#include<stdio.h>

#include<ctype.h>

int main()
{
	char data = '5';
	
	printf("is digit %d\n", isdigit(data));
	
	return 0;
}
```

```
OUTPUT

is digit 1
```

## C++ – `isdigit()` Example

```cpp id="i0l1xa"
#include <iostream>
#include <cctype>

using namespace std;

int main()
{
    char data = '5';

    cout << "is digit " << isdigit(data) << endl;

    return 0;
}
```

---

## Java – `Character.isDigit()` Example

```java id="yxvz56"
public class Main {
    public static void main(String[] args) {
        char data = '5';

        System.out.println("is digit " + (Character.isDigit(data) ? 1 : 0));
    }
}
```

---

## Python – `isdigit()` Example

```python id="14n8e4"
data = '5'

print("is digit", 1 if data.isdigit() else 0)
```

---

## Output

```text id="nkv4jv"
is digit 1
```

---

## Equivalent Functions

| Language | Function              |
| -------- | --------------------- |
| C        | `isdigit()`           |
| C++      | `isdigit()`           |
| Java     | `Character.isDigit()` |
| Python   | `isdigit()`           |

### More Examples

| Input | Result |
| ----- | ------ |
| `'5'` | 1      |
| `'0'` | 1      |
| `'9'` | 1      |
| `'a'` | 0      |
| `'@'` | 0      |

### Explanation

`isdigit()` checks whether a character is a numeric digit (`0`–`9`).

```text
isdigit('5') = 1
isdigit('0') = 1
isdigit('9') = 1
isdigit('a') = 0
isdigit('@') = 0
```

A return value of **1** (true) means the character is a digit, while **0** (false) means it is not.
