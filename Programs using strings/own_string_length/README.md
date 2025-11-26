# ✅ **C Version**

```
#include <stdio.h>

int string_length(char *data);

int main()
{
    printf("%d", string_length("prabhu"));

    return 0;
}

int string_length(char *data)
{
    int i = 0;
    
    while(data[i] != '\0')
    {
        i++;
    }
    
    return i;
}
```

Here are the **C++, Java, Python, and Tkinter versions** of your `string_length` program.

---

# ✅ **C++ Version**

```cpp
#include <iostream>
using namespace std;

int string_length(const char *data);

int main() {
    cout << string_length("prabhu");
    return 0;
}

int string_length(const char *data) {
    int i = 0;
    while (data[i] != '\0') {
        i++;
    }
    return i;
}
```

---

# ✅ **Java Version**

```java
public class Main {

    public static int stringLength(String data) {
        int i = 0;
        while (i < data.length()) {
            i++;
        }
        return i;
    }

    public static void main(String[] args) {
        System.out.println(stringLength("prabhu"));
    }
}
```

---

# ✅ **Python Version**

```python
def string_length(data):
    i = 0
    for _ in data:
        i += 1
    return i

print(string_length("prabhu"))
```

---

# ✅ **Tkinter GUI Version (Python)**

Shows input box + button + output label.

```python
import tkinter as tk

def string_length(data):
    i = 0
    for _ in data:
        i += 1
    return i

def calculate_length():
    text = entry.get()
    result = string_length(text)
    output_label.config(text=f"Length: {result}")

root = tk.Tk()
root.title("String Length Calculator")
root.geometry("300x200")

label = tk.Label(root, text="Enter text:")
label.pack(pady=5)

entry = tk.Entry(root, width=25)
entry.pack(pady=5)

button = tk.Button(root, text="Calculate", command=calculate_length)
button.pack(pady=10)

output_label = tk.Label(root, text="Length: ")
output_label.pack(pady=10)

root.mainloop()
```

---

If you want **Tkinter with real-time typing**, **OOP version**, or **character count including/excluding spaces**, let me know!
