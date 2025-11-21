```
#include <stdio.h>

int is_lower(char data);

int main()
{
    printf("%d", is_lower('a'));

    return 0;
}

int is_lower(char data)
{
    if(data >= 97 && data <= 122)
    {
        return 1;
    }
    else
    {
        return -1;
    }
}
```

Here is your **is_lower() program** rewritten in **C**, **C++**, **Java**, **Python**, and **Tkinter GUI**.
Your logic is correct — I’ll use `'a'` and `'z'` for clarity.

---

# ✅ **C Version**

```c
#include <stdio.h>

int is_lower(char data);

int main()
{
    printf("%d", is_lower('a'));
    return 0;
}

int is_lower(char data)
{
    if (data >= 'a' && data <= 'z')
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

int is_lower(char data) {
    if (data >= 'a' && data <= 'z')
        return 1;
    return -1;
}

int main() {
    cout << is_lower('a');
    return 0;
}
```

---

# ✅ **Java Version**

```java
public class LowerCheck {

    static int isLower(char ch) {
        if (ch >= 'a' && ch <= 'z')
            return 1;
        return -1;
    }

    public static void main(String[] args) {
        System.out.println(isLower('a'));
    }
}
```

---

# ✅ **Python Version**

```python
def is_lower(ch):
    if 'a' <= ch <= 'z':
        return 1
    return -1

print(is_lower('a'))
```

---

# ✅ **Tkinter GUI Version (Python)**

This GUI checks if the entered character is lowercase.

```python
import tkinter as tk

def check_lower():
    ch = entry.get()
    if len(ch) != 1:
        result.config(text="Enter 1 character only.")
        return

    if 'a' <= ch <= 'z':
        result.config(text="Lowercase (1)")
    else:
        result.config(text="Not lowercase (-1)")

root = tk.Tk()
root.title("Lowercase Checker")

tk.Label(root, text="Enter a character:").pack()

entry = tk.Entry(root)
entry.pack()

tk.Button(root, text="Check", command=check_lower).pack()

result = tk.Label(root, text="")
result.pack()

root.mainloop()
```

---

If you want, I can also prepare:

✔ **is_upper()**
✔ **is_digit()**
✔ **is_special_char()**
✔ **Combined program: Alphabet, Uppercase, Lowercase, Digit, Special**

Just ask!
