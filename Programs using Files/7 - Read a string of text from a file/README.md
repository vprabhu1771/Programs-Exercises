Below are **five versions** of your program (“Read a string of text from a file”) implemented in:

✅ **C**
✅ **C++**
✅ **Java**
✅ **Python**
✅ **Python Tkinter GUI**

---

# ✅ **1. C Program – Read string from file**

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    char c[1000];
    FILE *fptr;

    fptr = fopen("program.txt", "r");
    if (fptr == NULL) {
        printf("Error! opening file");
        exit(1);
    }

    fscanf(fptr, "%[^\n]", c);
    printf("Data from file:\n%s", c);

    fclose(fptr);
    return 0;
}
```

---

# ✅ **2. C++ Program – Read string from file**

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    ifstream file("program.txt");
    string line;

    if (!file) {
        cout << "Error opening file!";
        return 1;
    }

    getline(file, line);
    cout << "Data from file:\n" << line;

    file.close();
    return 0;
}
```

---

# ✅ **3. Java Program – Read string from file**

```java
import java.io.*;

class ReadFile {
    public static void main(String[] args) {
        try {
            BufferedReader br = new BufferedReader(new FileReader("program.txt"));
            String data = br.readLine();
            System.out.println("Data from file:\n" + data);
            br.close();
        } catch (Exception e) {
            System.out.println("Error opening file");
        }
    }
}
```

---

# ✅ **4. Python Program – Read string from file**

```python
try:
    with open("program.txt", "r") as f:
        data = f.readline()
        print("Data from file:\n", data)
except:
    print("Error opening file")
```

---

# ✅ **5. Tkinter GUI Program – Read file & show string**

```python
import tkinter as tk
from tkinter import messagebox

def read_file():
    try:
        with open("program.txt", "r") as f:
            data = f.readline()
        text_box.delete("1.0", tk.END)
        text_box.insert(tk.END, data)
    except:
        messagebox.showerror("Error", "Cannot open program.txt")

root = tk.Tk()
root.title("Read File Content")

btn = tk.Button(root, text="Read File", command=read_file)
btn.pack(pady=10)

text_box = tk.Text(root, width=40, height=5)
text_box.pack()

root.mainloop()
```

---

If you want, I can also give **GUI versions in C++ Qt, Java Swing/JavaFX**, or **save the output to another file**.
