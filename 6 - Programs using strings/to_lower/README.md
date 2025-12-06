# ✅ **C Version**

```
#include <stdio.h>

char to_lower(char data);

int main()
{
    printf("%c", to_lower('1'));

    return 0;
}

char to_lower(char data)
{
    if(data >= 65 && data <= 90) 
    {
        return data + 32;    
    }
    else
    {
        return data;
    }
    
}
```

Here are the **C++**, **Java**, **Python**, and **Tkinter** versions of your `to_lower()` program.

---

# ✅ **C++ Version**

```cpp
#include <iostream>
using namespace std;

char to_lower(char data) {
    if (data >= 'A' && data <= 'Z')
        return data + 32;
    else
        return data;
}

int main() {
    cout << to_lower('1');
    return 0;
}
```

---

# ✅ **Java Version**

```java
public class Main {

    public static char toLower(char data) {
        if (data >= 'A' && data <= 'Z') {
            return (char)(data + 32);
        } else {
            return data;
        }
    }

    public static void main(String[] args) {
        System.out.println(toLower('1'));
    }
}
```

---

# ✅ **Python Version**

```python
def to_lower(data):
    if 'A' <= data <= 'Z':
        return chr(ord(data) + 32)
    return data

print(to_lower('1'))
```

---

# ✅ **Tkinter GUI Version (Python)**

A simple GUI to convert a single character to lowercase.

```python
import tkinter as tk

def to_lower(data):
    if 'A' <= data <= 'Z':
        return chr(ord(data) + 32)
    return data

def convert():
    text = entry.get()
    if len(text) != 1:
        result_label.config(text="Enter exactly 1 character!")
    else:
        result_label.config(text="Lowercase: " + to_lower(text))

root = tk.Tk()
root.title("To Lower Converter")
root.geometry("300x180")

tk.Label(root, text="Enter a character:").pack(pady=5)

entry = tk.Entry(root, width=5)
entry.pack(pady=5)

tk.Button(root, text="Convert", command=convert).pack(pady=10)

result_label = tk.Label(root, text="Lowercase: ")
result_label.pack(pady=10)

root.mainloop()
```

---

If you want:

* Convert entire string
* Toggle-case
* Real-time conversion
  Just tell me!
