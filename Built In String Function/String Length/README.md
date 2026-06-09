# C
```c
#include<stdio.h>
#include<string.h>

int main()
{
    char name[80];

    printf("Enter name\n");
    scanf("%s", name);

    printf("String Length : %d", strlen(name));
    
    return 0;
}
```

Here is the equivalent program in **C++**, **Java**, and **Python** to find the length of a string entered by the user.

### C++

```cpp
#include <iostream>
#include <string>

using namespace std;

int main()
{
    string name;

    cout << "Enter name" << endl;
    cin >> name;

    cout << "String Length : " << name.length();

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

        System.out.println("String Length : " + name.length());

        sc.close();
    }
}
```

---

### Python

```python
name = input("Enter name: ")

print("String Length :", len(name))
```

### Example Output

```
Enter name
Prabhu
String Length : 6
```

### Note

* In **C**, `strlen(name)` returns the length of the string.
* In **C++**, `name.length()` or `name.size()` returns the length.
* In **Java**, `name.length()` returns the length.
* In **Python**, `len(name)` returns the length.

If you want to count spaces as well (e.g., `"Prabhu V"`), use:

* C: `fgets()`
* C++: `getline(cin, name)`
* Java: `sc.nextLine()`
* Python: `input()` already reads the entire line.
