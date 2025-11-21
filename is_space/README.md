```
#include <stdio.h>

int is_space(char data);

int main()
{
    printf("%d", is_space(' '));

    return 0;
}

int is_space(char data)
{
    if(data == 32)
    {
        return 1;
    }
    else
    {
        return -1;
    }
}
```

Here is your **is_space()** program written cleanly in **C**, **C++**, **Java**, **Python**, and **Tkinter GUI**.
Your logic is correct — I’ll use `' '` instead of ASCII **32** for readability.

---

# ✅ **C Version**

```c
#include <stdio.h>

int is_space(char data);

int main()
{
    printf("%d", is_space(' '));
    return 0;
}

int is_space(char data)
{
    if (data == ' ')
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

int is_space(char data) {
    if (data == ' ')
        return 1;
    return -1;
}

int main() {
    cout << is_space(' ');
    return 0;
}
```

---

# ✅ **Java Version**

```java
public class SpaceCheck {

    static int isSpace(char ch) {
        if (ch == ' ')
            return 1;
        return -1;
    }

    public static void main(String[] args) {
        System.out.println(isSpace(' '));
    }
}
```

---

# ✅ **Python Version**

```python
def is_space(ch):
    if ch == ' ':
        return 1
    return -1

print(is_space(' '))
```

---

# ✅ **Tkinter GUI Version (Python)**

GUI to check whether the entered character is a space.

```python
import tkinter as tk

def check_space():
    ch = entry.get()
    if len(ch) != 1:
        result.config(text="Enter 1 character only.")
        return

    if ch == ' ':
        result.config(text="Space (1)")
    else:
        result.config(text="Not space (-1)")

root = tk.Tk()
root.title("Space Checker")

tk.Label(root, text="Enter a character:").pack()

entry = tk.Entry(root)
entry.pack()

tk.Button(root, text="Check", command=check_space).pack()

result = tk.Label(root, text="")
result.pack()

root.mainloop()
```

---

If you want, I can also give:

✔ `is_digit()`
✔ `is_special()`
✔ Combined checker for **space, digit, alphabet, lowercase, uppercase**

Just ask!
