Your code is doing **number reversing**, not **digit summation**.
Digit summation means:

👉 Example
If **n = 1234** → **sum = 1+2+3+4 = 10**

Below are the **corrected digit summation programs** in **C, C++, Java, Python, Tkinter**.

---

# ✅ **1. C Program — Digit Summation**

```c
#include <stdio.h>

int main() {
    int sum = 0, m, n;

    printf("Enter the value of n: ");
    scanf("%d", &n);

    while (n != 0) {
        m = n % 10;
        n = n / 10;
        sum = sum + m;
    }

    printf("The sum of digits is %d\n", sum);

    return 0;
}
```

---

# ✅ **2. C++ Program — Digit Summation**

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, sum = 0;

    cout << "Enter the value of n: ";
    cin >> n;

    while (n != 0) {
        sum += n % 10;
        n /= 10;
    }

    cout << "The sum of digits is " << sum << endl;
    return 0;
}
```

---

# ✅ **3. Java Program — Digit Summation**

```java
import java.util.Scanner;

public class DigitSum {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter the value of n: ");
        int n = sc.nextInt();
        int sum = 0;

        while (n != 0) {
            sum += n % 10;
            n /= 10;
        }

        System.out.println("The sum of digits is " + sum);
    }
}
```

---

# ✅ **4. Python Program — Digit Summation**

```python
n = int(input("Enter the value of n: "))
sum = 0

while n != 0:
    sum += n % 10
    n //= 10

print("The sum of digits is", sum)
```

---

# ✅ **5. Tkinter GUI Program — Digit Summation**

```python
import tkinter as tk

def digit_sum():
    try:
        n = int(entry.get())
        s = 0

        temp = n
        while n != 0:
            s += n % 10
            n //= 10

        result_label.config(text=f"Sum of digits: {s}")
    except ValueError:
        result_label.config(text="Enter a valid integer")

root = tk.Tk()
root.title("Digit Summation")

tk.Label(root, text="Enter a number:").pack()

entry = tk.Entry(root)
entry.pack()

tk.Button(root, text="Calculate Sum", command=digit_sum).pack()

result_label = tk.Label(root, text="")
result_label.pack()

root.mainloop()
```

---

If you want, I can also give:

✔ Digit sum using recursion
✔ Digit sum using function
✔ Tkinter version with nice UI

Just tell me!
