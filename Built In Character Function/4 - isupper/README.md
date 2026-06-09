# C
```c
#include<stdio.h>

#include<ctype.h>

int main()
{
	char data = 'A';
	
	printf("is uppercase %d\n", isupper(data));
	
	return 0;
}
```
```
OUTPUT

is uppercase 1
```

## C++

```cpp
#include <iostream>
#include <cctype>

using namespace std;

int main()
{
    char data = 'A';

    cout << "is uppercase " << isupper(data) << endl;

    return 0;
}
```

---

## Java

```java
public class Main {
    public static void main(String[] args) {
        char data = 'A';

        System.out.println("is uppercase " +
                (Character.isUpperCase(data) ? 1 : 0));
    }
}
```

---

## Python

```python
data = 'A'

print("is uppercase", 1 if data.isupper() else 0)
```

---

## Output

```text
is uppercase 1
```

---

## Equivalent Functions

| Language | Function                  |
| -------- | ------------------------- |
| C        | `isupper()`               |
| C++      | `isupper()`               |
| Java     | `Character.isUpperCase()` |
| Python   | `isupper()`               |

### More Examples

| Input | Result |
| ----- | ------ |
| `'A'` | 1      |
| `'Z'` | 1      |
| `'a'` | 0      |
| `'5'` | 0      |
| `'@'` | 0      |

### Explanation

`isupper()` checks whether a character is an uppercase alphabet (`A`–`Z`).

```text
isupper('A') = 1
isupper('Z') = 1
isupper('a') = 0
isupper('5') = 0
isupper('@') = 0
```

A return value of **1** (true) means the character is uppercase, while **0** (false) means it is not.
