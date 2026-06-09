# C
```c
#include<stdio.h>

#include<string.h>

#define size 100

int main()
{
	char str1[size], str2[size];	

	puts("Enter your name");

	scanf("%s", str1);
		
	// string copy function first argument is destination
	// second argument is source
	strcpy(str2, str1);

	puts("copyed string");

	printf("%s\n", str2);

	return 0;
}
```
```
OUTPUT

Enter your name
prabhu

prabhu
```
## C++

```cpp id="4v7kqf"
#include <iostream>
#include <string>

using namespace std;

int main()
{
    string str1, str2;

    cout << "Enter your name" << endl;
    cin >> str1;

    str2 = str1;

    cout << "copied string" << endl;
    cout << str2 << endl;

    return 0;
}
```

---

## Java

```java id="jj8tzl"
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter your name");
        String str1 = sc.next();

        String str2 = str1;

        System.out.println("copied string");
        System.out.println(str2);

        sc.close();
    }
}
```

---

## Python

```python id="s4gjjp"
str1 = input("Enter your name: ")

str2 = str1

print("copied string")
print(str2)
```

---

## Output

```text id="n9yxck"
Enter your name
prabhu

copied string
prabhu
```

---

## Equivalent Operations

| Language | String Copy          |
| -------- | -------------------- |
| C        | `strcpy(str2, str1)` |
| C++      | `str2 = str1`        |
| Java     | `str2 = str1`        |
| Python   | `str2 = str1`        |

### Explanation

The value of `str1` is copied into `str2`.

```text id="pc2bl5"
str1 = "prabhu"
str2 = str1

Output:
prabhu
```

After copying:

```text id="kndnsu"
str1 -> prabhu
str2 -> prabhu
```

Both variables contain the same string value.
