### C

```c
#include <stdio.h>
#include <string.h>

int main()
{
    char name[80];

    printf("Enter name\n");
    scanf("%s", name);

    printf("%s", strlwr(name));

    return 0;
}
```

---

### C++

```cpp
#include <iostream>
#include <string>
#include <algorithm>

using namespace std;

int main()
{
    string name;

    cout << "Enter name" << endl;
    cin >> name;

    transform(name.begin(), name.end(), name.begin(), ::tolower);

    cout << name;

    return 0;
}
```

---

### Java

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter name");
        String name = sc.next();

        System.out.println(name.toLowerCase());

        sc.close();
    }
}
```

---

### Python

```python
name = input("Enter name: ")

print(name.lower())
```

---

### Example Output

```text
Enter name
PRABHU
prabhu
```

### Equivalent Functions

| Language | Lowercase Function          |
| -------- | --------------------------- |
| C        | `strlwr()`                  |
| C++      | `transform(..., ::tolower)` |
| Java     | `toLowerCase()`             |
| Python   | `lower()`                   |

> Note: `strlwr()` is compiler-specific and is not part of the standard C library. For portable C code, use `tolower()` from `<ctype.h>` in a loop.
