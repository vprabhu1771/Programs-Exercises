Here are **corrected and working versions** of your **String Comparison Program** in
**C, C++, Java, Python (Console), and Python Tkinter GUI** ✔️

Also → Removed unsafe `gets()`, removed `clrscr()` & `getch()`, and fixed the wrong loop condition.

---

## ✅ 1️⃣ **C Program — Compare Two Strings**

```c
#include <stdio.h>
#include <string.h>

int main() {
    char a[80], b[80];
    int i, equal = 1;

    printf("Enter string 1: ");
    fgets(a, sizeof(a), stdin);
    printf("Enter string 2: ");
    fgets(b, sizeof(b), stdin);

    // remove newline added by fgets if present
    a[strcspn(a, "\n")] = '\0';
    b[strcspn(b, "\n")] = '\0';

    // Compare
    if (strlen(a) != strlen(b)) {
        equal = 0;
    } else {
        for(i = 0; a[i] != '\0'; i++) {
            if(a[i] != b[i]) {
                equal = 0;
                break;
            }
        }
    }

    if (equal)
        printf("Strings are equal\n");
    else
        printf("Strings are not equal\n");

    return 0;
}
```

---

## 🟦 2️⃣ C++ Program

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main() {
    char a[80], b[80];

    cout << "Enter string 1: ";
    cin.getline(a, 80);

    cout << "Enter string 2: ";
    cin.getline(b, 80);

    if (strcmp(a, b) == 0)
        cout << "Strings are equal\n";
    else
        cout << "Strings are not equal\n";

    return 0;
}
```

---

## ☕ 3️⃣ Java Program

```java
import java.util.Scanner;

public class CompareStrings {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter string 1: ");
        String a = sc.nextLine();

        System.out.print("Enter string 2: ");
        String b = sc.nextLine();

        if (a.equals(b))
            System.out.println("Strings are equal");
        else
            System.out.println("Strings are not equal");

        sc.close();
    }
}
```

---

## 🐍 4️⃣ Python (Console)

```python
a = input("Enter string 1: ")
b = input("Enter string 2: ")

if a == b:
    print("Strings are equal")
else:
    print("Strings are not equal")
```

---

## 🖥️ 5️⃣ Python Tkinter GUI Program

```python
import tkinter as tk

def compare_strings():
    s1 = txt1.get()
    s2 = txt2.get()
    if s1 == s2:
        result.config(text="Strings are Equal", fg="green")
    else:
        result.config(text="Strings are Not Equal", fg="red")

root = tk.Tk()
root.title("String Comparison")

tk.Label(root, text="Enter String 1:").pack()
txt1 = tk.Entry(root, width=40)
txt1.pack(pady=5)

tk.Label(root, text="Enter String 2:").pack()
txt2 = tk.Entry(root, width=40)
txt2.pack(pady=5)

tk.Button(root, text="Compare", command=compare_strings).pack(pady=10)

result = tk.Label(root, text="", font=("Arial", 14))
result.pack(pady=10)

root.mainloop()
```

---

### If you want features like:

✔ Case-insensitive compare (“HELLO” = “hello”)
✔ Ignore spaces or special characters
✔ Compare lengths also

Tell me — I will update!
