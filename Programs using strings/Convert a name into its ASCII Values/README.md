# c

```c
#include<stdio.h>

#define SIZE 100

int main()
{
    char name[SIZE];

    int i;

    printf("Enter your name\n");

    scanf("%s", name);

    while(name[i] != '\0')
    {
        printf("%c = %d\n", name[i], name[i]);
        i++;
    }

    return 0;
}
```

Below are **C++**, **Java**, **Python**, and **Tkinter GUI** versions of your program.
Your original C code prints each character of the entered name along with its ASCII value.

---

# ✅ **C++ Version**

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main() {
    char name[100];
    int i = 0;

    cout << "Enter your name: ";
    cin >> name;

    while (name[i] != '\0') {
        cout << name[i] << " = " << (int)name[i] << endl;
        i++;
    }

    return 0;
}
```

---

# ✅ **Java Version**

```java
import java.util.Scanner;

public class NameAscii {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter your name: ");
        String name = sc.next();

        for (int i = 0; i < name.length(); i++) {
            System.out.println(name.charAt(i) + " = " + (int) name.charAt(i));
        }
    }
}
```

---

# ✅ **Python Version**

```python
name = input("Enter your name: ")

for ch in name:
    print(f"{ch} = {ord(ch)}")
```

---

# ✅ **Tkinter Version (Python GUI)**

```python
import tkinter as tk
from tkinter import messagebox

def show_ascii():
    name = entry.get()
    if not name:
        messagebox.showwarning("Warning", "Please enter a name")
        return
    
    result_text.delete("1.0", tk.END)
    
    for ch in name:
        result_text.insert(tk.END, f"{ch} = {ord(ch)}\n")

# GUI window
root = tk.Tk()
root.title("Name ASCII Viewer")
root.geometry("350x300")

label = tk.Label(root, text="Enter your name:")
label.pack(pady=5)

entry = tk.Entry(root, width=30)
entry.pack(pady=5)

btn = tk.Button(root, text="Show ASCII", command=show_ascii)
btn.pack(pady=10)

result_text = tk.Text(root, width=30, height=10)
result_text.pack(pady=5)

root.mainloop()
```

---

If you want, I can also give **C# Windows Forms**, **Flutter**, **JavaFX**, or **HTML + JavaScript** versions.
