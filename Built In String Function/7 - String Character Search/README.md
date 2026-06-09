# C
```c
#include<stdio.h>

#include<string.h>

#define size 100

int main()
{
	char name[size], search;

	puts("Enter your name");

	scanf("%s", name);
		
	printf("enter search character\n");

	scanf("%c", &search);

	if(strchr(name, search))
		puts("found");
	else
		puts("not found");

	return 0;
}
```
```
OUTPUT

Enter your name
prabhu

enter search character 
u

found
```

## C++

```cpp id="w7v4c8"
#include <iostream>
#include <string>

using namespace std;

int main()
{
    string name;
    char search;

    cout << "Enter your name" << endl;
    cin >> name;

    cout << "Enter search character" << endl;
    cin >> search;

    if (name.find(search) != string::npos)
        cout << "found" << endl;
    else
        cout << "not found" << endl;

    return 0;
}
```

---

## Java

```java id="e2j9k1"
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter your name");
        String name = sc.next();

        System.out.println("Enter search character");
        char search = sc.next().charAt(0);

        if (name.indexOf(search) != -1)
            System.out.println("found");
        else
            System.out.println("not found");

        sc.close();
    }
}
```

---

## Python

```python id="m5x8q2"
name = input("Enter your name: ")

search = input("Enter search character: ")

if search in name:
    print("found")
else:
    print("not found")
```

---

## Output

```text id="r4n7p6"
Enter your name
prabhu

Enter search character
u

found
```

---

## Equivalent Functions

| Language | Character Search       |
| -------- | ---------------------- |
| C        | `strchr(name, search)` |
| C++      | `name.find(search)`    |
| Java     | `name.indexOf(search)` |
| Python   | `search in name`       |

### Explanation

The program checks whether a character exists in a string.

```text id="v8c3n5"
String : prabhu
Search : u

Result : found
```

Another example:

```text id="k1p9t4"
String : prabhu
Search : z

Result : not found
```

> **Note:** In your C program, after `scanf("%s", name)`, use `scanf(" %c", &search)` (notice the space before `%c`) to skip the newline character left in the input buffer.
