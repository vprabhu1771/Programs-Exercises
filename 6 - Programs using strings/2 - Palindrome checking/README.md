Below are **corrected Palindrome Checking Programs** in
**C, C++, Java, Python (console), and Python Tkinter GUI** ✔️
I also fixed syntax errors, removed unsafe `gets()`, replaced wrong quotes, and improved logic.

---

# ✅ 1️⃣ C Program (Palindrome Check)

```c
#include <stdio.h>
#include <string.h>

int main() {
    char a[80];
    int i, j, k, c = 0;

    printf("Enter a string: ");
    fgets(a, sizeof(a), stdin);

    k = strlen(a) - 1;   // remove newline from fgets
    if (a[k] == '\n') a[k] = '\0';
    k = strlen(a);

    for (i = 0, j = k - 1; i < k / 2; i++, j--) {
        if (a[i] == a[j])
            c++;
    }

    if (c == k / 2)
        printf("Palindrome\n");
    else
        printf("Not Palindrome\n");

    return 0;
}
```

---

# 🟦 2️⃣ C++ Program

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main() {
    char a[80];
    int i, j, k, c = 0;

    cout << "Enter a string: ";
    cin.getline(a, 80);

    k = strlen(a);

    for (i = 0, j = k - 1; i < k / 2; i++, j--) {
        if (a[i] == a[j])
            c++;
    }

    if (c == k / 2)
        cout << "Palindrome\n";
    else
        cout << "Not Palindrome\n";

    return 0;
}
```

---

# ☕ 3️⃣ Java Program

```java
import java.util.Scanner;

public class Palindrome {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a string: ");
        String str = sc.nextLine();

        int k = str.length();
        int c = 0;

        for (int i = 0, j = k - 1; i < k / 2; i++, j--) {
            if (str.charAt(i) == str.charAt(j))
                c++;
        }

        if (c == k / 2)
            System.out.println("Palindrome");
        else
            System.out.println("Not Palindrome");

        sc.close();
    }
}
```

---

# 🐍 4️⃣ Python Program (Console)

```python
s = input("Enter a string: ")

if s == s[::-1]:
    print("Palindrome")
else:
    print("Not Palindrome")
```

---

# 🖥️ 5️⃣ Python Tkinter GUI Program

```python
import tkinter as tk

def check_palindrome():
    s = text.get()
    if s == s[::-1]:
        result.config(text="Palindrome", fg="green")
    else:
        result.config(text="Not Palindrome", fg="red")

root = tk.Tk()
root.title("Palindrome Checker")

tk.Label(root, text="Enter String:").pack()

text = tk.Entry(root, width=40)
text.pack(pady=10)

tk.Button(root, text="Check", command=check_palindrome).pack()

result = tk.Label(root, text="", font=("Arial", 14))
result.pack(pady=10)

root.mainloop()
```

---

### 👍 If you want:

✔ Ignore spaces & case (e.g., “Madam”, “A man a plan…”)
✔ Remove special characters
✔ Continuous checking while typing

Just tell me — I can enhance it!
