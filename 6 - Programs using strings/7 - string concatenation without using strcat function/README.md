Here are **corrected programs** for **string concatenation without using `strcat()`**
in **C, C++, Java, Python, and Python Tkinter GUI** ✔️

Your code issues fixed:

* Removed `gets()` (unsafe)
* Missing `#include <string.h>`
* Added **null-termination** of final string
* Removed `getch()` (not standard)

---

## ✅ 1️⃣ C Program — Manual Concatenation

```c
#include <stdio.h>
#include <string.h>

int main() {
    char a[80], b[80];
    int i, j;

    printf("Enter main string: ");
    fgets(a, sizeof(a), stdin);
    a[strcspn(a, "\n")] = '\0';  // remove newline added by fgets

    printf("Enter string to be concatenated: ");
    fgets(b, sizeof(b), stdin);
    b[strcspn(b, "\n")] = '\0';

    // find length of a
    i = strlen(a);

    // append b to a
    for (j = 0; b[j] != '\0'; j++, i++) {
        a[i] = b[j];
    }
    a[i] = '\0';  // terminate string

    printf("\nConcatenated string: %s\n", a);

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
    int i, j;

    cout << "Enter main string: ";
    cin.getline(a, 80);

    cout << "Enter string to concatenate: ";
    cin.getline(b, 80);

    i = strlen(a);

    for (j = 0; b[j] != '\0'; j++, i++) {
        a[i] = b[j];
    }
    a[i] = '\0';

    cout << "\nConcatenated string: " << a << endl;
    return 0;
}
```

---

## ☕ 3️⃣ Java Program (Manual Copy)

```java
import java.util.Scanner;

public class ConcatString {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter main string: ");
        String a = sc.nextLine();
        System.out.print("Enter string to concatenate: ");
        String b = sc.nextLine();

        // manual concatenation
        String result = "";
        for (int i = 0; i < a.length(); i++) result += a.charAt(i);
        for (int i = 0; i < b.length(); i++) result += b.charAt(i);

        System.out.println("\nConcatenated string: " + result);
        sc.close();
    }
}
```

---

## 🐍 4️⃣ Python Program (Manual Concatenation)

```python
a = input("Enter main string: ")
b = input("Enter string to concatenate: ")

result = ""
for ch in a:
    result += ch
for ch in b:
    result += ch

print("\nConcatenated string:", result)
```

---

## 🖥️ 5️⃣ Python Tkinter GUI Program

```python
import tkinter as tk

def concatenate_strings():
    s1 = entry1.get()
    s2 = entry2.get()
    result = ""

    for ch in s1:
        result += ch
    for ch in s2:
        result += ch

    output.config(text=f"Concatenated: {result}", fg="blue")

root = tk.Tk()
root.title("String Concatenation")

tk.Label(root, text="Main String:").pack()
entry1 = tk.Entry(root, width=40)
entry1.pack(pady=5)

tk.Label(root, text="String to Concatenate:").pack()
entry2 = tk.Entry(root, width=40)
entry2.pack(pady=5)

tk.Button(root, text="Concatenate", command=concatenate_strings).pack(pady=10)

output = tk.Label(root, text="", font=("Arial", 13))
output.pack(pady=10)

root.mainloop()
```

---

### Want enhancements?

✔ Remove spaces before concat
✔ Case-insensitive merge
✔ Join multiple strings
✔ GUI that updates live while typing

Tell me — I will extend!
