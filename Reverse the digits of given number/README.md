Here are the **correct and complete programs** for **C, C++, Java, Python, and Tkinter**, based on your code (reverse a number).

---

# ✅ **1. C Program (Reverse a Number)**

```c
#include <stdio.h>

int main() {
    long int num, r, sum = 0, giv;
    
    printf("Enter a number: ");
    scanf("%ld", &num);

    giv = num;

    while (num != 0) {
        r = num % 10;
        num = num / 10;
        sum = sum * 10 + r;
    }

    printf("Reversed number: %ld\n", sum);
    return 0;
}
```

---

# ✅ **2. C++ Program**

```cpp
#include <iostream>
using namespace std;

int main() {
    long long num, r, sum = 0, giv;

    cout << "Enter a number: ";
    cin >> num;

    giv = num;

    while (num != 0) {
        r = num % 10;
        num /= 10;
        sum = sum * 10 + r;
    }

    cout << "Reversed number: " << sum << endl;
    return 0;
}
```

---

# ✅ **3. Java Program**

```java
import java.util.Scanner;

public class ReverseNumber {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a number: ");
        long num = sc.nextLong();
        long giv = num;
        long sum = 0;

        while (num != 0) {
            long r = num % 10;
            num = num / 10;
            sum = sum * 10 + r;
        }

        System.out.println("Reversed number: " + sum);
    }
}
```

---

# ✅ **4. Python Program**

```python
num = int(input("Enter a number: "))
giv = num
sum = 0

while num != 0:
    r = num % 10
    num //= 10
    sum = sum * 10 + r

print("Reversed number:", sum)
```

---

# ✅ **5. Tkinter GUI Program (Reverse a Number)**

```python
import tkinter as tk

def reverse_number():
    try:
        num = int(entry.get())
        giv = num
        rev = 0

        while num != 0:
            r = num % 10
            num //= 10
            rev = rev * 10 + r

        result_label.config(text=f"Reversed number: {rev}")
    except ValueError:
        result_label.config(text="Enter a valid integer")

root = tk.Tk()
root.title("Reverse Number")

tk.Label(root, text="Enter a number:").pack()

entry = tk.Entry(root)
entry.pack()

tk.Button(root, text="Reverse", command=reverse_number).pack()

result_label = tk.Label(root, text="")
result_label.pack()

root.mainloop()
```

---

If you want, I can also give:

✔ palindrome check (same number forward & backward)
✔ version using recursion
✔ version using string slicing

Just tell me!
