Here are **corrected programs** for **copying one string into another without using `strcpy()`**
in **C, C++, Java, Python (console), and Python Tkinter GUI** ✔️

Your submitted code had issues:

* `gets()` is unsafe → replaced with `fgets()`
* Missing `#include <string.h>`
* Removed `clrscr()` (not standard)
* Correct null-termination after copy

---

## ✅ 1️⃣ C Program (Manual String Copy)

```c
#include <stdio.h>
#include <string.h>

int main() {
    char src[80], dest[80];
    int i;

    printf("Enter source string: ");
    fgets(src, sizeof(src), stdin);
    src[strcspn(src, "\n")] = '\0'; // remove newline

    for (i = 0; src[i] != '\0'; i++) {
        dest[i] = src[i];
    }
    dest[i] = '\0'; // terminate string

    printf("\nCopied string: %s\n", dest);

    return 0;
}
```

---

## 🟦 2️⃣ C++ Program

```cpp
#include <iostream>
using namespace std;

int main() {
    char src[80], dest[80];
    int i;

    cout << "Enter source string: ";
    cin.getline(src, 80);

    for (i = 0; src[i] != '\0'; i++)
        dest[i] = src[i];
    dest[i] = '\0';

    cout << "\nCopied string: " << dest << endl;
    return 0;
}
```

---

## ☕ 3️⃣ Java Program

(Manual char-by-char copy using array)

```java
import java.util.Scanner;

public class CopyString {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter string: ");
        String src = sc.nextLine();
        char[] dest = new char[src.length()];

        for (int i = 0; i < src.length(); i++) {
            dest[i] = src.charAt(i);
        }

        System.out.println("\nCopied string: " + new String(dest));
        sc.close();
    }
}
```

---

## 🐍 4️⃣ Python Program (Manual Copy)

```python
src = input("Enter string: ")

dest = ""
for ch in src:
    dest += ch

print("\nCopied string:", dest)
```

---

## 🖥️ 5️⃣ Python Tkinter GUI Program

```python
import tkinter as tk

def copy_string():
    src = entry.get()
    dest = ""
    for ch in src:
        dest += ch
    result.config(text=f"Copied String: {dest}", fg="blue")

root = tk.Tk()
root.title("Manual String Copy")

tk.Label(root, text="Enter String:").pack()

entry = tk.Entry(root, width=40)
entry.pack(pady=10)

tk.Button(root, text="Copy", command=copy_string).pack(pady=10)

result = tk.Label(root, text="", font=("Arial", 13))
result.pack(pady=10)

root.mainloop()
```

---

### Want Extra Features? 😎

✔ Copy only part of the string
✔ Show copied string length
✔ Upper/Lower-case conversion during copy

Tell me — I will add it!
