Your code is doing **reverse** instead of **Armstrong check**.

## ✅ Armstrong Number Rule

A number is Armstrong if:

**sum of (each digit³) = number**
(For 3-digit numbers)

Example:
153 → 1³ + 5³ + 3³ = 153 ✔

---

# ✅ 1. **C Program — Armstrong Number**

```c
#include <stdio.h>

int main() {
    int num, ams, r, sum = 0;

    printf("Enter a number: ");
    scanf("%d", &num);

    ams = num;

    while (num != 0) {
        r = num % 10;
        sum = sum + (r * r * r);   // cube of digit
        num = num / 10;
    }

    if (ams == sum)
        printf("%d is an Armstrong number\n", ams);
    else
        printf("%d is not an Armstrong number\n", ams);

    return 0;
}
```

---

# ✅ 2. **C++ Program — Armstrong Number**

```cpp
#include <iostream>
using namespace std;

int main() {
    int num, ams, r, sum = 0;

    cout << "Enter a number: ";
    cin >> num;

    ams = num;

    while (num != 0) {
        r = num % 10;
        sum += (r * r * r);
        num /= 10;
    }

    if (ams == sum)
        cout << ams << " is an Armstrong number";
    else
        cout << ams << " is not an Armstrong number";

    return 0;
}
```

---

# ✅ 3. **Java Program — Armstrong Number**

```java
import java.util.Scanner;

public class Armstrong {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a number: ");
        int num = sc.nextInt();

        int ams = num;
        int sum = 0;

        while (num != 0) {
            int r = num % 10;
            sum += (r * r * r);
            num /= 10;
        }

        if (ams == sum)
            System.out.println(ams + " is an Armstrong number");
        else
            System.out.println(ams + " is not an Armstrong number");
    }
}
```

---

# ✅ 4. **Python Program — Armstrong Number**

```python
num = int(input("Enter a number: "))

ams = num
sum = 0

while num != 0:
    r = num % 10
    sum += r ** 3
    num //= 10

if ams == sum:
    print(f"{ams} is an Armstrong number")
else:
    print(f"{ams} is not an Armstrong number")
```

---

# ✅ 5. **Tkinter Program — Armstrong Number**

```python
import tkinter as tk

def check_armstrong():
    try:
        num = int(entry.get())
        ams = num
        s = 0

        while num != 0:
            r = num % 10
            s += r ** 3
            num //= 10

        if s == ams:
            result_label.config(text=f"{ams} is an Armstrong number")
        else:
            result_label.config(text=f"{ams} is not an Armstrong number")
    except:
        result_label.config(text="Enter a valid number")

root = tk.Tk()
root.title("Armstrong Number Checker")

tk.Label(root, text="Enter a number:").pack()

entry = tk.Entry(root)
entry.pack()

tk.Button(root, text="Check Armstrong", command=check_armstrong).pack()

result_label = tk.Label(root, text="")
result_label.pack()

root.mainloop()
```

---

If you want, I can also provide:

✔ Armstrong for **n-digit** number
✔ Tkinter version with better UI
✔ Armstrong using **function** or **recursion**

Just tell me!
