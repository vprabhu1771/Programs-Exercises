Here are **cleaned and corrected programs** for **removing all characters except alphabets** in **C, C++, Java, Python, and Tkinter GUI**.

Your original C code had issues:

* `gets()` is unsafe → replaced with `fgets()`
* Parentheses mismatch in condition
* Improved loop logic

---

## ✅ 1️⃣ C Program

```c
#include <stdio.h>

int main() {
    char line[150];
    int i, j;

    printf("Enter a string: ");
    fgets(line, sizeof(line), stdin);

    for (i = 0; line[i] != '\0'; ++i) {
        while (!( (line[i] >= 'a' && line[i] <= 'z') || 
                  (line[i] >= 'A' && line[i] <= 'Z') || 
                  line[i] == '\0')) {
            for (j = i; line[j] != '\0'; ++j) {
                line[j] = line[j + 1];
            }
        }
    }

    printf("Output String: %s\n", line);
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
    string str;
    cout << "Enter a string: ";
    getline(cin, str);

    for (size_t i = 0; i < str.length(); ) {
        if (!isalpha(str[i])) {
            str.erase(i, 1);
        } else {
            i++;
        }
    }

    cout << "Output String: " << str << endl;
    return 0;
}
```

---

## ✅ 3️⃣ Java Program

```java
import java.util.Scanner;

public class RemoveNonAlphabets {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a string: ");
        String str = sc.nextLine();
        String result = "";

        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);
            if (Character.isLetter(ch)) {
                result += ch;
            }
        }

        System.out.println("Output String: " + result);
        sc.close();
    }
}
```

---

## ✅ 4️⃣ Python Program

```python
s = input("Enter a string: ")
result = ''.join(ch for ch in s if ch.isalpha())
print("Output String:", result)
```

---

## ✅ 5️⃣ Python Tkinter GUI Program

```python
import tkinter as tk

def clean_string():
    s = entry.get()
    result = ''.join(ch for ch in s if ch.isalpha())
    output.config(text=f"Output String: {result}")

root = tk.Tk()
root.title("Remove Non-Alphabet Characters")

tk.Label(root, text="Enter a string:").pack()
entry = tk.Entry(root, width=40)
entry.pack(pady=5)

tk.Button(root, text="Remove", command=clean_string).pack(pady=10)

output = tk.Label(root, text="", font=("Arial", 12))
output.pack(pady=10)

root.mainloop()
```

---

If you want, I can also make a **version that keeps spaces** while removing numbers and symbols — useful for **sentence cleaning**.

Do you want me to do that?
