```
#include <stdio.h>

int is_upper(char data);

int main()
{
    printf("%d", is_upper('A'));

    return 0;
}

int is_upper(char data)
{
    if(data >= 65 && data <= 90)
    {
        return 1;
    }
    else
    {
        return -1;
    }
}
```

Here is your **is_upper()** program rewritten cleanly in **C**, **C++**, **Java**, **Python**, and **Tkinter GUI**.

Your logic is correct — using `'A'` and `'Z'` makes it more readable.

---

# ✅ **C Version**

```c
#include <stdio.h>

int is_upper(char data);

int main()
{
    printf("%d", is_upper('A'));
    return 0;
}

int is_upper(char data)
{
    if (data >= 'A' && data <= 'Z')
        return 1;
    else
        return -1;
}
```

---

# ✅ **C++ Version**

```cpp
#include <iostream>
using namespace std;

int is_upper(char data) {
    if (data >= 'A' && data <= 'Z')
        return 1;
    return -1;
}

int main() {
    cout << is_upper('A');
    return 0;
}
```

---

# ✅ **Java Version**

```java
public class UpperCheck {

    static int isUpper(char ch) {
        if (ch >= 'A' && ch <= 'Z')
            return 1;
        return -1;
    }

    public static void main(String[] args) {
        System.out.println(isUpper('A'));
    }
}
```

---

# ✅ **Python Version**

```python
def is_upper(ch):
    if 'A' <= ch <= 'Z':
        return 1
    return -1

print(is_upper('A'))
```

---

# ✅ **Tkinter GUI Version (Python)**

```python
import tkinter as tk

def check_upper():
    ch = entry.get()
    if len(ch) != 1:
        result.config(text="Enter 1 character only.")
        return

    if 'A' <= ch <= 'Z':
        result.config(text="Uppercase (1)")
    else:
        result.config(text="Not uppercase (-1)")

root = tk.Tk()
root.title("Uppercase Checker")

tk.Label(root, text="Enter a character:").pack()

entry = tk.Entry(root)
entry.pack()

tk.Button(root, text="Check", command=check_upper).pack()

result = tk.Label(root, text="")
result.pack()

root.mainloop()
```

---

If you want, I can also provide:

✔ `is_digit()`
✔ `is_special()`
✔ Combined program for **upper, lower, digit, alphabet, space**
✔ Tkinter version with color indicators

Just tell me!
