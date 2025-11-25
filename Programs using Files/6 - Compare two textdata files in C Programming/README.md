Below are **clean, corrected, safe, modern versions** of your
**Compare Two Text/Data Files Program** in:

✅ **C**
✅ **C++**
✅ **Java**
✅ **Python**
✅ **Tkinter GUI**

Your original C code had issues:
✔ `gets()` is unsafe → replaced with `scanf("%s", filename)`
✔ Smart EOF handling
✔ Quotes (“ ”) fixed to (" ")

---

# ✅ **C Program – Compare Two Files**

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *fp1, *fp2;
    int ch1, ch2;
    char fname1[40], fname2[40];

    printf("Enter name of first file: ");
    scanf("%s", fname1);

    printf("Enter name of second file: ");
    scanf("%s", fname2);

    fp1 = fopen(fname1, "r");
    fp2 = fopen(fname2, "r");

    if (fp1 == NULL) {
        printf("Cannot open %s for reading\n", fname1);
        exit(1);
    }
    if (fp2 == NULL) {
        printf("Cannot open %s for reading\n", fname2);
        exit(1);
    }

    while (1) {
        ch1 = fgetc(fp1);
        ch2 = fgetc(fp2);

        if (ch1 != ch2)
            break;

        if (ch1 == EOF || ch2 == EOF)
            break;
    }

    if (ch1 == ch2)
        printf("Files are IDENTICAL\n");
    else
        printf("Files are NOT IDENTICAL\n");

    fclose(fp1);
    fclose(fp2);
    return 0;
}
```

---

# ✅ **C++ Program – Compare Two Files**

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    string f1, f2;

    cout << "Enter first file: ";
    cin >> f1;
    cout << "Enter second file: ";
    cin >> f2;

    ifstream file1(f1), file2(f2);

    if (!file1) { cout << "Cannot open " << f1 << endl; return 1; }
    if (!file2) { cout << "Cannot open " << f2 << endl; return 1; }

    char ch1, ch2;
    bool identical = true;

    while (file1.get(ch1) && file2.get(ch2)) {
        if (ch1 != ch2) {
            identical = false;
            break;
        }
    }

    if (identical && file1.eof() == file2.eof())
        cout << "Files are IDENTICAL\n";
    else
        cout << "Files are NOT IDENTICAL\n";

    return 0;
}
```

---

# ✅ **Java Program – Compare Two Files**

```java
import java.io.*;

public class CompareFiles {
    public static void main(String[] args) {
        try {
            BufferedReader br1 = new BufferedReader(new FileReader("test1.txt"));
            BufferedReader br2 = new BufferedReader(new FileReader("test2.txt"));

            int ch1, ch2;
            boolean identical = true;

            while ((ch1 = br1.read()) != -1 && (ch2 = br2.read()) != -1) {
                if (ch1 != ch2) {
                    identical = false;
                    break;
                }
            }

            if (identical && br1.read() == br2.read())
                System.out.println("Files are IDENTICAL");
            else
                System.out.println("Files are NOT IDENTICAL");

            br1.close();
            br2.close();

        } catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

---

# ✅ **Python Program – Compare Two Files**

```python
def compare_files(f1, f2):
    with open(f1, "r") as file1, open(f2, "r") as file2:
        while True:
            ch1 = file1.read(1)
            ch2 = file2.read(1)

            if ch1 != ch2:
                return False

            if ch1 == "" and ch2 == "":
                return True

file1 = "test1.txt"
file2 = "test2.txt"

if compare_files(file1, file2):
    print("Files are IDENTICAL")
else:
    print("Files are NOT IDENTICAL")
```

---

# ✅ **Tkinter GUI – Compare Two Files (Browse & Compare)**

```python
import tkinter as tk
from tkinter import filedialog, messagebox

def select_file1():
    global file1
    file1 = filedialog.askopenfilename()
    label1.config(text=file1)

def select_file2():
    global file2
    file2 = filedialog.askopenfilename()
    label2.config(text=file2)

def compare():
    if not file1 or not file2:
        messagebox.showwarning("Warning", "Select both files!")
        return

    try:
        with open(file1, "r") as f1, open(file2, "r") as f2:
            while True:
                c1 = f1.read(1)
                c2 = f2.read(1)

                if c1 != c2:
                    messagebox.showinfo("Result", "Files are NOT IDENTICAL")
                    return

                if c1 == "" and c2 == "":
                    break

        messagebox.showinfo("Result", "Files are IDENTICAL")

    except Exception as e:
        messagebox.showerror("Error", str(e))

root = tk.Tk()
root.title("File Compare Tool")

file1 = file2 = None

tk.Button(root, text="Select First File", command=select_file1).pack(pady=5)
label1 = tk.Label(root, text="No file selected")
label1.pack()

tk.Button(root, text="Select Second File", command=select_file2).pack(pady=5)
label2 = tk.Label(root, text="No file selected")
label2.pack()

tk.Button(root, text="Compare Files", command=compare, bg="lightblue").pack(pady=20)

root.mainloop()
```

---

# Do you want?

✔ Line-by-line comparison
✔ Highlight first mismatch
✔ Tkinter version with side-by-side text viewer
✔ Compare binary files

Just tell me!
