# C
```c
#include<stdio.h>
#include<string.h>

int main()
{
    char name[80];

    printf("Enter name\n");
    scanf("%s", name);

    printf("%s", strupr(name));

    return 0;
}
```

Your C program converts a string to **uppercase** using `strupr()`.

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

    transform(name.begin(), name.end(), name.begin(), ::toupper);

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

        System.out.println(name.toUpperCase());

        sc.close();
    }
}
```

---

### Python

```python
name = input("Enter name: ")

print(name.upper())
```

### Example Output

```
Enter name
prabhu
PRABHU
```

### Equivalent Functions

| Language | Uppercase Function          |
| -------- | --------------------------- |
| C        | `strupr()`                  |
| C++      | `transform(..., ::toupper)` |
| Java     | `toUpperCase()`             |
| Python   | `upper()`                   |

> Note: `strupr()` is not part of the ANSI C standard and may not be available in all C compilers.
