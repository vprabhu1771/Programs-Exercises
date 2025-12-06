Here are **cleaned and corrected programs** for **reversing a string** in **C, C++, Java, Python, and Tkinter GUI**.

Your original C code works, but I made improvements:

* Handle strings with spaces (`scanf("%s",...)` → `fgets()` in C)
* Removed non-standard practices (`void main()`)

---

## ✅ 1️⃣ C Program

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[50], rev[50];
    int i = 0, j = 0;

    printf("Enter any string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0'; // remove newline

    int len = strlen(str);

    for(i = len - 1; i >= 0; i--) {
        rev[j++] = str[i];
    }
    rev[j] = '\0';

    printf("Reverse of string is: %s\n", rev);
    return 0;
}
```

---

## ✅ 2️⃣ C++ Program

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string str, rev = "";
    cout << "Enter any string: ";
    getline(cin, str);

    for(int i = str.length() - 1; i >= 0; i--)
        rev += str[i];

    cout << "Reverse of string is: " << rev << endl;
    return 0;
}
```

---

## ✅ 3️⃣ Java Program

```java
import java.util.Scanner;

public class ReverseString {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter any string: ");
        String str = sc.nextLine();
        String rev = "";

        for(int i = str.length() - 1; i >= 0; i--) {
            rev += str.charAt(i);
        }

        System.out.println("Reverse of string is: " + rev);
        sc.close();
    }
}
```

---

## ✅ 4️⃣ Python Program

```python
s = input("Enter any string: ")
rev = s[::-1]
print("Reverse of string is:", rev)
```

---

## ✅ 5️⃣ Python Tkinter GUI Program

```python
import tkinter as tk

def reverse_string():
    s = entry.get()
    rev = s[::-1]
    output.config(text=f"Reverse of string: {rev}")

root = tk.Tk()
root.title("String Reverser")

tk.Label(root, text="Enter string:").pack()
entry = tk.Entry(root, width=40)
entry.pack(pady=5)

tk.Button(root, text="Reverse", command=reverse_string).pack(pady=10)

output = tk.Label(root, text="", font=("Arial", 12))
output.pack(pady=10)

root.mainloop()
```

---

If you want, I can make an **in-place reverse version** in C/C++ **without using extra array** to save memory.

Do you want me to do that?
