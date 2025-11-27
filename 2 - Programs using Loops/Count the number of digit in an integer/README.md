Here are the **corrected programs** for **C, C++, Java, Python, and Tkinter (Python GUI)** that count the number of digits in an integer.

---

# ✅ **1. C Program (Corrected)**

```c
#include <stdio.h>

int main() {
    int n, count = 0;

    printf("Enter an integer: ");
    scanf("%d", &n);

    if (n == 0) {
        count = 1;
    } else {
        if (n < 0) {
            n = -n; // handle negative numbers
        }

        while (n != 0) {
            n /= 10;
            count++;
        }
    }

    printf("Number of digits: %d\n", count);
    return 0;
}
```

---

# ✅ **2. C++ Program**

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, count = 0;

    cout << "Enter an integer: ";
    cin >> n;

    if (n == 0) {
        count = 1;
    } else {
        if (n < 0) n = -n;

        while (n != 0) {
            n /= 10;
            count++;
        }
    }

    cout << "Number of digits: " << count << endl;
    return 0;
}
```

---

# ✅ **3. Java Program**

```java
import java.util.Scanner;

public class CountDigits {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter an integer: ");
        int n = sc.nextInt();
        int count = 0;

        if (n == 0) {
            count = 1;
        } else {
            n = Math.abs(n);

            while (n != 0) {
                n /= 10;
                count++;
            }
        }

        System.out.println("Number of digits: " + count);
    }
}
```

---

# ✅ **4. Python Program**

```python
n = int(input("Enter an integer: "))
count = 0

if n == 0:
    count = 1
else:
    n = abs(n)

    while n != 0:
        n //= 10
        count += 1

print("Number of digits:", count)
```

---

# ✅ **5. Tkinter GUI Program (Python)**

```python
import tkinter as tk

def count_digits():
    try:
        n = int(entry.get())
        if n == 0:
            count = 1
        else:
            n = abs(n)
            count = 0
            while n != 0:
                n //= 10
                count += 1
        result_label.config(text=f"Number of digits: {count}")
    except ValueError:
        result_label.config(text="Please enter a valid integer")

root = tk.Tk()
root.title("Digit Counter")

tk.Label(root, text="Enter an integer:").pack()

entry = tk.Entry(root)
entry.pack()

tk.Button(root, text="Count Digits", command=count_digits).pack()

result_label = tk.Label(root, text="")
result_label.pack()

root.mainloop()
```

---

If you want, I can also provide:

✔ version using recursion
✔ version using logarithms
✔ a modern Tkinter UI design

Just tell me!
