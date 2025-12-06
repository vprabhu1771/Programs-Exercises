Below are **corrected and working** programs in **C, C++, Java, Python (Console), and Python Tkinter GUI** to count **Blanks, Tabs, and Newlines**.
The input will stop when you press `*` (asterisk).

---

## ✅ **1️⃣ C Program**

> Fix: Replace wrong quotes `’` with `'` and include proper formatting.

```c
#include <stdio.h>

int main() {
    int nb = 0, nt = 0, nl = 0;
    int c;

    printf("Enter text (Press * to stop):\n");

    while ((c = getchar()) != '*') {
        if (c == ' ')
            nb++;
        else if (c == '\t')
            nt++;
        else if (c == '\n')
            nl++;
    }

    printf("\nNo. of Blanks = %d", nb);
    printf("\nNo. of Tabs = %d", nt);
    printf("\nNo. of Newlines = %d\n", nl);

    return 0;
}
```

---

## 🟦 **2️⃣ C++ Program**

```cpp
#include <iostream>
using namespace std;

int main() {
    int nb = 0, nt = 0, nl = 0;
    char c;

    cout << "Enter text (Press * to stop):\n";

    while (cin.get(c) && c != '*') {
        if (c == ' ') nb++;
        else if (c == '\t') nt++;
        else if (c == '\n') nl++;
    }

    cout << "\nBlanks: " << nb;
    cout << "\nTabs: " << nt;
    cout << "\nNewlines: " << nl << endl;
    return 0;
}
```

---

## ☕ **3️⃣ Java Program**

```java
import java.io.*;

public class CountChars {
    public static void main(String[] args) throws IOException {
        int nb = 0, nt = 0, nl = 0;
        System.out.println("Enter text (Press * to stop):");

        while (true) {
            int c = System.in.read();
            if (c == '*')
                break;

            if (c == ' ')
                nb++;
            else if (c == '\t')
                nt++;
            else if (c == '\n')
                nl++;
        }

        System.out.println("Blanks = " + nb);
        System.out.println("Tabs = " + nt);
        System.out.println("Newlines = " + nl);
    }
}
```

---

## 🐍 **4️⃣ Python (Console Program)**

```python
print("Enter text (Press * then Enter to stop):")

nb = nt = nl = 0

while True:
    ch = input()
    if '*' in ch:  # stop if * found
        break
    for c in ch:
        if c == ' ':
            nb += 1
        elif c == '\t':
            nt += 1
    nl += 1  # each input() adds a newline

print("Blanks:", nb)
print("Tabs:", nt)
print("Newlines:", nl)
```

---

## 🖥️ **5️⃣ Python Tkinter GUI Program**

👉 Enter text and click **Count**

```python
import tkinter as tk

def count_chars():
    text = input_text.get("1.0", "end")
    nb = text.count(" ")
    nt = text.count("\t")
    nl = text.count("\n") - 1  # Tk adds an extra newline at end
    result_label.config(
        text=f"Blanks: {nb} | Tabs: {nt} | Newlines: {nl}"
    )

root = tk.Tk()
root.title("Blank, Tab, Newline Counter")

input_text = tk.Text(root, width=40, height=10)
input_text.pack(padx=10, pady=10)

btn = tk.Button(root, text="Count", command=count_chars)
btn.pack()

result_label = tk.Label(root, text="")
result_label.pack(pady=10)

root.mainloop()
```

---

### 👍 If you need:

✔ File handling version
✔ Stop on ENTER only
✔ Show counts live while typing

Just tell me — I can modify!
