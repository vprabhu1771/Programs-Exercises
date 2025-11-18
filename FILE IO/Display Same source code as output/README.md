# C

```c
#include<stdio.h>

int main()
{
    FILE *fp;
    char ch;

    fp = fopen(__FILE__, "r");

    do
    {
        ch = getc(fp);
        putchar(ch);
    }
    while( ch != EOF );

  fclose(fp);

  return 0;
}
```
Below are the **C++**, **Java**, **Python**, and **Tkinter (Python GUI)** versions of your program.

Your C code prints its own source code (simple self-replicating program).
All versions below do the same.

---

# ✅ **C++ Version**

```cpp
#include <iostream>
#include <fstream>

int main() {
    std::ifstream file(__FILE__);
    char ch;

    while (file.get(ch)) {
        std::cout << ch;
    }

    file.close();
    return 0;
}
```

---

# ✅ **Java Version**

Java does not have `__FILE__`, so give the filename manually.

Save as **SelfPrint.java**:

```java
import java.io.FileReader;

public class SelfPrint {
    public static void main(String[] args) {
        String fileName = "SelfPrint.java";

        try (FileReader fr = new FileReader(fileName)) {
            int ch;
            while ((ch = fr.read()) != -1) {
                System.out.print((char) ch);
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

---

# ✅ **Python Version**

Python cannot detect its own filename reliably in all cases,
but `__file__` works when running from a file.

```python
with open(__file__, "r") as f:
    print(f.read(), end="")
```

---

# ✅ **Tkinter Version (GUI Window showing its own source code)**

Save this as **self_viewer.py**:

```python
import tkinter as tk
from tkinter import scrolledtext
import sys
import os

root = tk.Tk()
root.title("Self Viewer")

text_area = scrolledtext.ScrolledText(root, width=80, height=30)
text_area.pack()

# get current file name
filename = os.path.abspath(__file__)

with open(filename, "r") as f:
    content = f.read()

text_area.insert(tk.END, content)
text_area.config(state="disabled")

root.mainloop()
```

---

If you want, I can also give **C#, PHP, Flutter Dart**, or **JavaFX** versions.
