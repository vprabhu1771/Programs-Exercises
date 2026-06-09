# C
```c
#include<stdio.h>

#include<ctype.h>

int main()
{
	char data = 'a';
	
	printf("is lowercase %d\n", islower(data));
	
	return 0;
}
```
```
OUTPUT

is lowercase 1
```

## C++

```cpp
#include <iostream>
#include <cctype>

using namespace std;

int main()
{
    char data = 'a';

    cout << "is lowercase " << islower(data) << endl;

    return 0;
}
```

---

## Java

```java
public class Main {
    public static void main(String[] args) {
        char data = 'a';

        System.out.println("is lowercase " +
                (Character.isLowerCase(data) ? 1 : 0));
    }
}
```

---

## Python

```python
data = 'a'

print("is lowercase", 1 if data.islower() else 0)
```

---

## Output

```text
is lowercase 1
```

---

## Equivalent Functions

| Language | Function                  |
| -------- | ------------------------- |
| C        | `islower()`               |
| C++      | `islower()`               |
| Java     | `Character.isLowerCase()` |
| Python   | `islower()`               |

### More Examples

| Input | Result |
| ----- | ------ |
| `'a'` | 1      |
| `'z'` | 1      |
| `'A'` | 0      |
| `'5'` | 0      |
| `'@'` | 0      |

### Explanation

`islower()` checks whether a character is a lowercase alphabet (`a`–`z`).

```text
islower('a') = 1
islower('z') = 1
islower('A') = 0
islower('5') = 0
islower('@') = 0
```

A return value of **1** (true) means the character is lowercase, while **0** (false) means it is not.
