Here are **working examples** for **C, C++, Java, Python, and Python Tkinter**, each writing a sentence to a file.

---

# ✅ **C Program – Write a Sentence to a File**

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    char c[1000];
    FILE *fptr;

    fptr = fopen("program.txt", "w");
    if (fptr == NULL) {
        printf("Error opening file!");
        exit(1);
    }

    printf("Enter a sentence:\n");
    fgets(c, sizeof(c), stdin);

    fprintf(fptr, "%s", c);
    fclose(fptr);

    printf("File written successfully.\n");
    return 0;
}
```

---

# ✅ **C++ Program – Write a Sentence to a File**

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    string sentence;
    ofstream file("program.txt");

    if (!file) {
        cout << "Error opening file!";
        return 1;
    }

    cout << "Enter a sentence:\n";
    getline(cin, sentence);

    file << sentence;
    file.close();

    cout << "File written successfully.\n";
    return 0;
}
```

---

# ✅ **Java Program – Write a Sentence to a File**

```java
import java.io.FileWriter;
import java.io.IOException;
import java.util.Scanner;

public class WriteToFile {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        try {
            FileWriter fw = new FileWriter("program.txt");

            System.out.println("Enter a sentence:");
            String text = sc.nextLine();

            fw.write(text);
            fw.close();
            System.out.println("File written successfully.");

        } catch (IOException e) {
            System.out.println("Error: " + e.getMessage());
        }

        sc.close();
    }
}
```

---

# ✅ **Python Program – Write a Sentence to a File**

```python
sentence = input("Enter a sentence:\n")

with open("program.txt", "w") as f:
    f.write(sentence)

print("File written successfully.")
```

---

# ✅ **Python Tkinter Program – Write a Sentence to a File**

```python
import tkinter as tk
from tkinter import messagebox

def write_file():
    text = entry.get()
    with open("program.txt", "w") as f:
        f.write(text)
    messagebox.showinfo("Success", "File written successfully!")

root = tk.Tk()
root.title("Write to File")

label = tk.Label(root, text="Enter a sentence:")
label.pack(pady=5)

entry = tk.Entry(root, width=40)
entry.pack(pady=5)

button = tk.Button(root, text="Save to File", command=write_file)
button.pack(pady=10)

root.mainloop()
```

---

If you want, I can also provide **GUI versions for C/C++**, or **Tkinter with multi-line text box**, or **file choosing dialog**.
