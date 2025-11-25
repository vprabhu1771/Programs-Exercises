Below are **correct, safe, modern versions** of your **Copy File Content Program** in **C, C++, Java, Python, and Tkinter GUI**.

Your original C code had a small mistake:
`fgetc()` returns **int**, not char — because `EOF = -1`.

All versions below use correct handling.

---

# ✅ **C Program – Copy one file to another (Corrected)**

```c
#include <stdio.h>
#include <stdlib.h>

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
        fputc(ch, fp2);
    }

    fclose(fp1);
    fclose(fp2);

    printf("File copied successfully!\n");
    return 0;
}
```

---

# ✅ **C++ Program – Copy File**

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    ifstream src("test.txt", ios::binary);
    ofstream dest("test1.txt", ios::binary);

    if (!src) {
        cout << "Cannot open source file\n";
        return 1;
    }
    if (!dest) {
        cout << "Cannot open destination file\n";
        return 1;
    }

    dest << src.rdbuf();

    cout << "File copied successfully!\n";
    return 0;
}
```

---

# ✅ **Java Program – Copy File**

```java
import java.io.*;

public class CopyFile {
    public static void main(String[] args) {
        try {
            FileInputStream in = new FileInputStream("test.txt");
            FileOutputStream out = new FileOutputStream("test1.txt");

            int c;
            while ((c = in.read()) != -1) {
                out.write(c);
            }

            in.close();
            out.close();
            System.out.println("File copied successfully!");
        } catch (Exception e) {
            System.out.println("File error: " + e);
        }
    }
}
```

---

# ✅ **Python Program – Copy File**

```python
with open("test.txt", "r") as f1, open("test1.txt", "w") as f2:
    for line in f1:
        f2.write(line)

print("File copied successfully!")
```

---

# ✅ **Tkinter GUI – Select a File & Copy to Another**

This GUI allows user to select source file and copies it to **test1.txt**.

```python
import tkinter as tk
from tkinter import filedialog, messagebox

def copy_file():
    src = filedialog.askopenfilename(title="Select Source File")
    if not src:
        return

    dest = "test1.txt"

    try:
        with open(src, "r") as f1, open(dest, "w") as f2:
            for line in f1:
                f2.write(line)

        messagebox.showinfo("Success", "File copied successfully to test1.txt")
    except Exception as e:
        messagebox.showerror("Error", str(e))

root = tk.Tk()
root.title("File Copy")

tk.Button(root, text="Select File & Copy", command=copy_file).pack(pady=20)

root.mainloop()
```

---

If you want, I can also provide:

✔ Tkinter version with destination file chooser
✔ Binary file copy
✔ Text area preview before copying
✔ Progress bar version

Just tell me!
