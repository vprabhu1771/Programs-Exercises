### C

```c
#include <stdio.h>
#include <string.h>

int main()
{
    char name[80];

    printf("Enter name\n");
    scanf("%s", name);

    printf("%s", strrev(name));

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

    reverse(name.begin(), name.end());

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

        String reversed = new StringBuilder(name).reverse().toString();

        System.out.println(reversed);

        sc.close();
    }
}
```

---

### Python

```python
name = input("Enter name: ")

print(name[::-1])
```

---

### Example Output

```text
Enter name
PRABHU
UHBARP
```

### Equivalent Functions

| Language | Reverse Method            |
| -------- | ------------------------- |
| C        | `strrev()`                |
| C++      | `reverse()`               |
| Java     | `StringBuilder.reverse()` |
| Python   | `[::-1]` (slicing)        |

> Note: `strrev()` is not part of the standard C library. For portable C code, reverse the string manually using a loop.
