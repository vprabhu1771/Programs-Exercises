# C
```c
#include<stdio.h>

#include<ctype.h>

int main()
{
	char data = 'a';
	
	printf("%c\n", toupper(data));
	
	return 0;
}
```
```
OUTPUT

A
```

## C++

```cpp
#include <iostream>
#include <cctype>

using namespace std;

int main()
{
    char data = 'a';

    cout << (char)toupper(data) << endl;

    return 0;
}
```

---

## Java

```java
public class Main {
    public static void main(String[] args) {
        char data = 'a';

        System.out.println(Character.toUpperCase(data));
    }
}
```

---

## Python

```python
data = 'a'

print(data.upper())
```

---

## Output

```text
A
```

---

## Equivalent Functions

| Language | Function                  |
| -------- | ------------------------- |
| C        | `toupper()`               |
| C++      | `toupper()`               |
| Java     | `Character.toUpperCase()` |
| Python   | `upper()`                 |

### More Examples

| Input | Output |
| ----- | ------ |
| `'a'` | `'A'`  |
| `'z'` | `'Z'`  |
| `'A'` | `'A'`  |
| `'5'` | `'5'`  |
| `'@'` | `'@'`  |

### Explanation

`toupper()` converts a lowercase letter to its uppercase equivalent.

```text
toupper('a') = 'A'
toupper('z') = 'Z'
toupper('A') = 'A'
toupper('5') = '5'
```

If the character is not a lowercase alphabet, it remains unchanged.
