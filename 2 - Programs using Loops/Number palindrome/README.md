Below are the **correct and complete programs** for **Number Palindrome** in **C, C++, Java, Python, and Tkinter (GUI)** based on your code.

---

# ✅ **1. C Program (Number Palindrome)**

```c
#include <stdio.h>

int main() {
    long int num, r, sum = 0, temp;

    printf("Enter a number: ");
    scanf("%ld", &num);

    temp = num;

    while (num != 0) {
        r = num % 10;
        num = num / 10;
        sum = sum * 10 + r;
    }

    if (temp == sum)
        printf("%ld is a palindrome\n", temp);
    else
        printf("%ld is not a palindrome\n", temp);

    return 0;
}
```

---

# ✅ **2. C++ Program**

```cpp
#include <iostream>
using namespace std;

int main() {
    long long num, r, sum = 0, temp;

    cout << "Enter a number: ";
    cin >> num;

    temp = num;

    while (num != 0) {
        r = num % 10;
        num /= 10;
        sum = sum * 10 + r;
    }

    if (temp == sum)
        cout << temp << " is a palindrome" << endl;
    else
        cout << temp << " is not a palindrome" << endl;

    return 0;
}
```

---

# ✅ **3. Java Program**

```java
import java.util.Scanner;

public class PalindromeNumber {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a number: ");
        long num = sc.nextLong();
        long temp = num;
        long sum = 0;

        while (num != 0) {
            long r = num % 10;
            num /= 10;
            sum = sum * 10 + r;
        }

        if (temp == sum)
            System.out.println(temp + " is a palindrome");
        else
            System.out.println(temp + " is not a palindrome");
    }
}
```

---

# ✅ **4. Python Program**

```python
num = int(input("Enter a number: "))
temp = num
sum = 0

while num != 0:
    r = num % 10
    num //= 10
    sum = sum * 10 + r

if temp == sum:
    print(f"{temp} is a palindrome")
else:
    print(f"{temp} is not a palindrome")
```

---

# ✅ **5. Tkinter GUI Program (Number Palindrome)**

```python
import tkinter as tk

def check_palindrome():
    try:
        num = int(entry.get())
        temp = num
        rev = 0

        while num != 0:
            r = num % 10
            num //= 10
            rev = rev * 10 + r

        if temp == rev:
            result_label.config(text=f"{temp} is a palindrome")
        else:
            result_label.config(text=f"{temp} is not a palindrome")
    except ValueError:
        result_label.config(text="Enter a valid integer")

root = tk.Tk()
root.title("Palindrome Number Checker")

tk.Label(root, text="Enter a number:").pack()

entry = tk.Entry(root)
entry.pack()

tk.Button(root, text="Check Palindrome", command=check_palindrome).pack()

result_label = tk.Label(root, text="")
result_label.pack()

root.mainloop()
```

---

If you want, I can also provide:

✔ Palindrome checker for strings
✔ Tkinter version with better UI
✔ Recursive palindrome program

Just tell me!
