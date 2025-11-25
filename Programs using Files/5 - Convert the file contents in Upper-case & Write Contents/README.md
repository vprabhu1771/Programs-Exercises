Below are **correct, modern, working versions** of:

### ✅ Convert file contents to **UPPERCASE** and write to another file

in **C, C++, Java, Python, and Tkinter GUI**.

Your original C code had issues:
✔ `fgetc()` must be **int**, not char
✔ Must check `EOF` before using `toupper()`
✔ `fcloseall()` is outdated – replaced with `fclose()`

---

# ✅ **C Program – Convert File to Uppercase**

```c
#include <stdio.h>
#include <stdlib.h>
#include <ctype.h>

int main() {
    FILE *fp1, *fp2;
    int ch;

    fp1 = fopen("test.txt", "r");
    if (fp1 == NULL) {
        printf("Cannot open source file\n");
        exit(1);
    }

    fp2 = fopen("test1.txt", "w");
    if (fp2 == NULL) {
        printf("Cannot open destination file\n");
        fclose(fp1);
        exit(1);
    }

    while ((ch = fgetc(fp1)) != EOF) {
        ch = toupper(ch);
        fputc(ch, fp2);
    }

    fclose(fp1);
    fclose(fp2);

    printf("File converted to uppercase successfully!\n");
    return 0;
}
```

---

# ✅ **C++ Program – Convert File to Uppercase**

```cpp
#include <iostream>
#include <fstream>
#include <cctype>
using namespace std;

int main() {
    ifstream src("test.txt");
    ofstream dest("test1.txt");

    if (!src) { cout << "Cannot open source file\n"; return 1; }
    if (!dest) { cout << "Cannot open destination file\n"; return 1; }

    char ch;
    while (src.get(ch)) {
        dest << (char)toupper(ch);
    }

    cout << "File converted to uppercase successfully!\n";
    return 0;
}
```

---

# ✅ **Java Program – Convert File to Uppercase**

```java
import java.io.*;

public class UpperFile {
    public static void main(String[] args) {
        try {
            FileReader fr = new FileReader("test.txt");
            FileWriter fw = new FileWriter("test1.txt");

            int c;
            while ((c = fr.read()) != -1) {
                fw.write(Character.toUpperCase(c));
            }

            fr.close();
            fw.close();

            System.out.println("File converted to uppercase successfully!");
        } catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

---

# ✅ **Python Program – Convert File to Uppercase**

```python
with open("test.txt", "r") as f1, open("test1.txt", "w") as f2:
    for line in f1:
        f2.write(line.upper())

print("File converted to uppercase successfully!")
```

---

# ✅ **Tkinter GUI Program – Select a File & Convert to Uppercase**

This GUI allows user to pick any input file and converts it into **UPPERCASE** and saves as **output_upper.txt**.

```python
import tkinter as tk
from tkinter import filedialog, messagebox

def convert_uppercase():
    src = filedialog.askopenfilename(title="Select Input File")
    if not src:
        return

    dest = "output_upper.txt"

    try:
        with open(src, "r") as f1, open(dest, "w") as f2:
            for line in f1:
                f2.write(line.upper())

        messagebox.showinfo("Success", "File converted to uppercase!")
    except Exception as e:
        messagebox.showerror("Error", str(e))

root = tk.Tk()
root.title("Uppercase File Converter")

tk.Button(root, text="Select File & Convert to Uppercase", 
          command=convert_uppercase).pack(pady=20)

root.mainloop()
```

---

If you want, I can also provide:

✔ Tkinter version with save-as dialog
✔ Real-time text preview + uppercase conversion
✔ Uppercase + lowercase + title-case options

Just tell me!
