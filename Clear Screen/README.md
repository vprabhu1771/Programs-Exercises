# c
```c
#include <stdio.h>
#include <stdlib.h>

int main() {

    #ifdef _WIN32
        system("cls");
    #else
        system("clear");
    #endif

  return 0;
}
```

Here are **equivalent screen-clear examples** in **C++, Java, Python (console)** and **Tkinter GUI**.

---

# ✅ **C++ (Your Original Code)**

```cpp
#include <iostream>
#include <cstdlib>

int main() {

#ifdef _WIN32
    system("cls");
#else
    system("clear");
#endif

    return 0;
}
```

---

# ✅ **Java Equivalent**

Java does not have a built-in `cls` or `clear`, so use ANSI escape codes (works on Linux/Mac & Windows 10+):

```java
public class ClearScreen {
    public static void main(String[] args) {
        System.out.print("\033[H\033[2J");
        System.out.flush();
    }
}
```

**Windows CMD (old versions)** will not support this. Then you must run:

```java
Runtime.getRuntime().exec("cmd /c cls");
```

But this is not recommended.

---

# ✅ **Python Console Clear**

### Cross-platform console clear:

```python
import os

# Windows
if os.name == 'nt':
    os.system('cls')
# Linux/Mac
else:
    os.system('clear')
```

Or **ANSI escape code** (faster):

```python
print("\033[H\033[2J", end="")
```

---

# ✅ **Tkinter Clear Equivalent (GUI)**

Tkinter doesn’t have a “screen clear” like console.
But you can **clear all widgets in the window**:

```python
import tkinter as tk

root = tk.Tk()

def clear_screen():
    for widget in root.winfo_children():
        widget.destroy()

tk.Button(root, text="Clear Screen", command=clear_screen).pack()

root.mainloop()
```

If you want to clear a **Frame only**:

```python
def clear_frame(frame):
    for widget in frame.winfo_children():
        widget.destroy()
```

---

# If you want, I can also make:

✔ A single program showing all four
✔ Buttons to clear console + Tkinter output
✔ A reusable clear function for any platform

Just tell me!
