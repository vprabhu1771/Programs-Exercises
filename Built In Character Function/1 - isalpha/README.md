# C
```c
#include<stdio.h>

#include<ctype.h>

int main()
{
	char data = 'a';
	
	printf("is alphabet %d\n", isalpha(data));
	
	return 0;
}
```
```
OUTPUT

is alphabet 1
```

## C++

```cpp
#include <iostream>
#include <cctype>

using namespace std;

int main()
{
    char data = 'a';

    cout << "is alphabet " << isalpha(data) << endl;

    return 0;
}
```

---

## Java

```java
public class Main {
    public static void main(String[] args) {
        char data = 'a';

        System.out.println("is alphabet " + (Character.isLetter(data) ? 1 : 0));
    }
}
```

---

## Python

```python
data = 'a'

print("is alphabet", 1 if data.isalpha() else 0)
```

---

## Output

```text
is alphabet 1
```

---

## Equivalent Functions

| Language | Function               |
| -------- | ---------------------- |
| C        | `isalpha()`            |
| C++      | `isalpha()`            |
| Java     | `Character.isLetter()` |
| Python   | `isalpha()`            |

### More Examples

| Input | Result |
| ----- | ------ |
| `'a'` | 1      |
| `'Z'` | 1      |
| `'5'` | 0      |
| `'@'` | 0      |
| `' '` | 0      |

### Explanation

`isalpha()` checks whether a character is an alphabetic letter (`A-Z` or `a-z`).

```text
isalpha('a') = 1
isalpha('Z') = 1
isalpha('5') = 0
isalpha('@') = 0
```

A return value of `1` (or true) means the character is a letter, while `0` (or false) means it is not.
