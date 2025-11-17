# ✅ **C Version**

```
#include <stdio.h>

char to_upper(char data);

int main()
{
    printf("%c", to_upper('a'));

    return 0;
}

char to_upper(char data)
{
    if(data >= 97 && data <= 122) 
    {
        return data - 32;    
    }
    else
    {
        return data;
    }
    
}
```

Below are the **C++**, **Java**, **Python**, and **Tkinter** versions of your `to_upper` function program (same logic as your C code).

---

# ✅ **C++ Version**

```cpp
#include <iostream>
using namespace std;

char to_upper(char data) {
    if (data >= 'a' && data <= 'z')
        return data - 32;
    else
        return data;
}

int main() {
    cout << to_upper('a');
    return 0;
}
```

---

# ✅ **Java Version**

```java
public class Main {

    public static char toUpper(char data) {
        if (data >= 'a' && data <= 'z') {
            return (char)(data - 32);
        } else {
            return data;
        }
    }

    public static void main(String[] args) {
        System.out.println(toUpper('a'));
    }
}
```

---

# ✅ **Python Version**

```python
def to_upper(data):
    if 'a' <= data <= 'z':
        return chr(ord(data) - 32)
    return data

print(to_upper('a'))
```

---

# ✅ **Tkinter Version (Python GUI)**

A small GUI to convert one character to uppercase:

```python
import tkinter as tk

def to_upper(data):
    if 'a' <= data <= 'z':
        return chr(ord(data) - 32)
    return data

def convert():
    text = entry.get()
    if len(text) != 1:
        result_label.config(text="Enter 1 character only!")
    else:
        result_label.config(text="Uppercase: " + to_upper(text))

root = tk.Tk()
root.title("To Upper Converter")
root.geometry("300x180")

tk.Label(root, text="Enter a character:").pack(pady=5)

entry = tk.Entry(root, width=5)
entry.pack(pady=5)

tk.Button(root, text="Convert", command=convert).pack(pady=10)

result_label = tk.Label(root, text="Uppercase: ")
result_label.pack(pady=10)

root.mainloop()
```

---

If you want:
✅ Convert whole string
✅ Toggle case
✅ Real-time typing uppercasing
Just tell me!
