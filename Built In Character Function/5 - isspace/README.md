# C
```c
#include<stdio.h>

#include<ctype.h>

int main()
{
	char data = ' ';
	
	printf("is spacebar %d\n", isspace(data));
	
	return 0;
}
```
```
OUTPUT

is spacebar 1
```

## C++ – `isspace()` Example

```cpp
#include <iostream>
#include <cctype>

using namespace std;

int main()
{
    char data = ' ';

    cout << "is spacebar " << isspace(data) << endl;

    return 0;
}
```

---

## Java – `Character.isWhitespace()` Example

```java
public class Main {
    public static void main(String[] args) {
        char data = ' ';

        System.out.println("is spacebar " +
                (Character.isWhitespace(data) ? 1 : 0));
    }
}
```

---

## Python – `isspace()` Example

```python
data = ' '

print("is spacebar", 1 if data.isspace() else 0)
```

---

## Output

```text
is spacebar 1
```

---

## Equivalent Functions

| Language | Function                   |
| -------- | -------------------------- |
| C        | `isspace()`                |
| C++      | `isspace()`                |
| Java     | `Character.isWhitespace()` |
| Python   | `isspace()`                |

### More Examples

| Input            | Result |
| ---------------- | ------ |
| `' '` (space)    | 1      |
| `'\t'` (tab)     | 1      |
| `'\n'` (newline) | 1      |
| `'A'`            | 0      |
| `'5'`            | 0      |

### Explanation

`isspace()` checks whether a character is a whitespace character such as:

* Space (`' '`)
* Tab (`'\t'`)
* Newline (`'\n'`)
* Carriage Return (`'\r'`)
* Form Feed (`'\f'`)
* Vertical Tab (`'\v'`)

```text
isspace(' ')  = 1
isspace('\t') = 1
isspace('\n') = 1
isspace('A')  = 0
isspace('5')  = 0
```

A return value of **1** (true) means the character is whitespace, while **0** (false) means it is not.
