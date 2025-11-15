Here is the **same program rewritten in C, C++, Java, Python, and Python Tkinter**, all showing **monitor screen width & height**.

---

# ✅ **C**

```c
#include <stdio.h>
#include <windows.h>

int main()
{
    int width, height;

    width = GetSystemMetrics(SM_CXSCREEN);
    height = GetSystemMetrics(SM_CYSCREEN);

    printf("Size of your monitor is %d by %d.\n", width, height);

    return 0;
}
```

---

# ✅ **C++ Version**

```cpp
#include<iostream>
#include<windows.h>

int main()
{
    int width, height;

    width = GetSystemMetrics(SM_CXSCREEN);

    height = GetSystemMetrics(SM_CYSCREEN);

    std::cout << "Size of your monitor is " << width << " by " << height << endl

    return 0;
}
```

---

# ✅ **Java Version**

Java uses `Toolkit` to get screen size:

```java
import java.awt.Dimension;
import java.awt.Toolkit;

public class ScreenSize {
    public static void main(String[] args) {
        Dimension screenSize = Toolkit.getDefaultToolkit().getScreenSize();
        int width = (int) screenSize.getWidth();
        int height = (int) screenSize.getHeight();

        System.out.println("Size of your monitor is " + width + " by " + height);
    }
}
```

---

# ✅ **Python Version**

```python
import tkinter as tk

root = tk.Tk()
root.withdraw()

width = root.winfo_screenwidth()
height = root.winfo_screenheight()

print(f"Size of your monitor is {width} by {height}.")
```

---

# ✅ **Python Tkinter GUI Version**

```python
import tkinter as tk

root = tk.Tk()
root.title("Screen Resolution")

width = root.winfo_screenwidth()
height = root.winfo_screenheight()

label = tk.Label(root, 
                 text=f"Size of your monitor is {width} x {height}",
                 font=("Arial", 20))
label.pack(pady=50)

root.mainloop()
```

---

# ✅ Output Example

```
Size of your monitor is 1920 by 1080.
```

---

If you want versions for **Linux**, **Mac**, **C#**, **Flutter**, or **WinForms**, tell me—I can provide those too!
