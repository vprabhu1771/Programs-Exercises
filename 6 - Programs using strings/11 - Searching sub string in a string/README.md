Here are clean and corrected **Substring Searching** programs in **C, C++, Java, and Python** based on your logic (character-by-character matching).

---

## ✅ **C Program: Search Substring in a String**

```c
#include <stdio.h>

void main() {
    char str[80], search[10];
    int count1 = 0, count2 = 0, i, j, flag = 0;

    printf("Enter a string:\n");
    while ((str[count1] = getchar()) != '\n')
        count1++;
    str[count1] = '\0';

    printf("Enter search substring:\n");
    while ((search[count2] = getchar()) != '\n')
        count2++;
    search[count2] = '\0';

    for (i = 0; i <= count1 - count2; i++) {
        flag = 1;
        for (j = 0; j < count2; j++) {
            if (str[i + j] != search[j]) {
                flag = 0;
                break;
            }
        }
        if (flag == 1)
            break;
    }

    if (flag == 1)
        printf("SEARCH SUCCESSFUL!\n");
    else
        printf("SEARCH UNSUCCESSFUL!\n");
}
```

---

## ✅ **C++ Program**

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string str, sub;
    
    cout << "Enter main string: ";
    getline(cin, str);

    cout << "Enter substring to search: ";
    getline(cin, sub);

    if (str.find(sub) != string::npos)
        cout << "SEARCH SUCCESSFUL!";
    else
        cout << "SEARCH UNSUCCESSFUL!";

    return 0;
}
```

---

## ✅ **Java Program**

```java
import java.util.Scanner;

public class SubstringSearch {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter main string: ");
        String str = sc.nextLine();

        System.out.println("Enter substring to search: ");
        String sub = sc.nextLine();

        if (str.contains(sub))
            System.out.println("SEARCH SUCCESSFUL!");
        else
            System.out.println("SEARCH UNSUCCESSFUL!");
    }
}
```

---

## ✅ **Python Program**

```python
str_input = input("Enter main string: ")
search = input("Enter substring to search: ")

if search in str_input:
    print("SEARCH SUCCESSFUL!")
else:
    print("SEARCH UNSUCCESSFUL!")
```

---

### Want Tkinter version also?

✔ Show input boxes
✔ Button to search
✔ Display result in label box

Just tell me — I can provide it too!
