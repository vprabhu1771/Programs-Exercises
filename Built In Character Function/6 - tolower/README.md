# C
```c
#include<stdio.h>

#include<ctype.h>

int main()
{
	char data = 'A';
	
	printf("%c\n", tolower(data));
	
	return 0;
}
```
```
OUTPUT

a
```

## C++

```cpp id="93zd3m"
#include <iostream>
#include <cctype>

using namespace std;

int main()
{
    char data = 'A';

    cout << (char)tolower(data) << endl;

    return 0;
}
```

---

## Java

```java id="hxyq0d"
public class Main {
    public static void main(String[] args) {
        char data = 'A';

        System.out.println(Character.toLowerCase(data));
    }
}
```

---

## Python

```python id="1x4hjh"
data = 'A'

print(data.lower())
```

---

## Output

```text id="kvp2ws"
a
```

---

## Equivalent Functions

| Language | Function                  |
| -------- | ------------------------- |
| C        | `tolower()`               |
| C++      | `tolower()`               |
| Java     | `Character.toLowerCase()` |
| Python   | `lower()`                 |

### More Examples

| Input | Output |
| ----- | ------ |
| `'A'` | `'a'`  |
| `'Z'` | `'z'`  |
| `'a'` | `'a'`  |
| `'5'` | `'5'`  |
| `'@'` | `'@'`  |

### Explanation

`tolower()` converts an uppercase letter to its lowercase equivalent.

```text
tolower('A') = 'a'
tolower('Z') = 'z'
tolower('a') = 'a'
tolower('5') = '5'
```

If the character is not an uppercase alphabet, it remains unchanged.
