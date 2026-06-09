# C
```c
#include<stdio.h>

#include<string.h>

#define size 100

int main()
{
	char name[size], search[size];

	puts("Enter any string");

	scanf("%s", data);
		
	printf("enter search string\n");

	scanf("%s", search);

	if(strstr(data, search))
		puts("found");
	else
		puts("not found");

	return 0;
}
```
```
OUTPUT

Enter any string
i am from cuddalore

enter search string
from

found
```

## C++ – Substring Search (`find()`)

```cpp id="c8m4q1"
#include <iostream>
#include <string>

using namespace std;

int main()
{
    string data, search;

    cout << "Enter any string" << endl;
    getline(cin, data);

    cout << "Enter search string" << endl;
    getline(cin, search);

    if (data.find(search) != string::npos)
        cout << "found" << endl;
    else
        cout << "not found" << endl;

    return 0;
}
```

---

## Java – Substring Search (`contains()`)

```java id="j7x2n9"
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter any string");
        String data = sc.nextLine();

        System.out.println("Enter search string");
        String search = sc.nextLine();

        if (data.contains(search))
            System.out.println("found");
        else
            System.out.println("not found");

        sc.close();
    }
}
```

---

## Python – Substring Search (`in`)

```python id="p5v8k3"
data = input("Enter any string: ")

search = input("Enter search string: ")

if search in data:
    print("found")
else:
    print("not found")
```

---

## Output

```text id="t9w4m6"
Enter any string
i am from cuddalore

Enter search string
from

found
```

---

## Equivalent Functions

| Language | Substring Search        |
| -------- | ----------------------- |
| C        | `strstr(data, search)`  |
| C++      | `data.find(search)`     |
| Java     | `data.contains(search)` |
| Python   | `search in data`        |

### Explanation

This program checks whether a string exists inside another string.

```text id="g2n8q7"
Main String : i am from cuddalore
Search String : from

Result : found
```

Another example:

```text id="k4p1v9"
Main String : i am from cuddalore
Search String : chennai

Result : not found
```

### Corrected C Program

Your C code has a small mistake. You declared `name` but used `data`.

```c
char data[size], search[size];

scanf("%s", data);

if(strstr(data, search))
    puts("found");
else
    puts("not found");
```

Also, if you want to search strings containing spaces (`"i am from cuddalore"`), use `fgets()` instead of `scanf("%s", ...)`.
