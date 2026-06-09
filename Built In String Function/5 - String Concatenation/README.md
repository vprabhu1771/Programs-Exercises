### C

```c
#include <stdio.h>
#include <string.h>

int main()
{
    char str1[80], str2[80];

    printf("Enter first string\n");
    scanf("%s", str1);

    printf("Enter second string\n");
    scanf("%s", str2);

    strcat(str1, str2);

    printf("Concatenated String: %s", str1);

    return 0;
}
```

---

### C++

```cpp
#include <iostream>
#include <string>

using namespace std;

int main()
{
    string str1, str2;

    cout << "Enter first string" << endl;
    cin >> str1;

    cout << "Enter second string" << endl;
    cin >> str2;

    string result = str1 + str2;

    cout << "Concatenated String: " << result;

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

        System.out.println("Enter first string");
        String str1 = sc.next();

        System.out.println("Enter second string");
        String str2 = sc.next();

        String result = str1 + str2;

        System.out.println("Concatenated String: " + result);

        sc.close();
    }
}
```

---

### Python

```python
str1 = input("Enter first string: ")
str2 = input("Enter second string: ")

result = str1 + str2

print("Concatenated String:", result)
```

---

### Example Output

```text
Enter first string
Hello
Enter second string
World
Concatenated String: HelloWorld
```

### Equivalent Functions

| Language | Concatenation        |
| -------- | -------------------- |
| C        | `strcat(str1, str2)` |
| C++      | `str1 + str2`        |
| Java     | `str1 + str2`        |
| Python   | `str1 + str2`        |

> Note: In C, ensure the destination array (`str1`) has enough space to hold both strings after concatenation.
