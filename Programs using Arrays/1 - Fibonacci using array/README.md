Below are clean and correct **Fibonacci using Array** programs in:

✔ **C**
✔ **C++**
✔ **Java**
✔ **Python**
✔ **Python Tkinter GUI**

---

# ✅ **C Program – Fibonacci Using Array**

```c
#include <stdio.h>

int main() {
    int n, i;
    int fib[25];

    scanf("%d", &n);

    fib[0] = 0;
    fib[1] = 1;

    for (i = 2; i <= n; i++)
        fib[i] = fib[i - 2] + fib[i - 1];

    for (i = 0; i <= n; i++)
        printf("%d\n", fib[i]);

    return 0;
}
```

---

# ✅ **C++ Program – Fibonacci Using Array**

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    int fib[25];

    cin >> n;

    fib[0] = 0;
    fib[1] = 1;

    for (int i = 2; i <= n; i++)
        fib[i] = fib[i - 2] + fib[i - 1];

    for (int i = 0; i <= n; i++)
        cout << fib[i] << endl;

    return 0;
}
```

---

# ✅ **Java Program – Fibonacci Using Array**

```java
import java.util.Scanner;

public class FibonacciArray {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n;

        n = sc.nextInt();

        int[] fib = new int[25];

        fib[0] = 0;
        fib[1] = 1;

        for (int i = 2; i <= n; i++)
            fib[i] = fib[i - 2] + fib[i - 1];

        for (int i = 0; i <= n; i++)
            System.out.println(fib[i]);
    }
}
```

---

# ✅ **Python Program – Fibonacci Using List**

```python
n = int(input())
fib = [0] * 25

fib[0] = 0
fib[1] = 1

for i in range(2, n + 1):
    fib[i] = fib[i - 2] + fib[i - 1]

for i in range(n + 1):
    print(fib[i])
```

---

# ✅ **Python Tkinter GUI – Fibonacci Using Array**

Enter `n`, display first `n` Fibonacci numbers.

```python
import tkinter as tk
from tkinter import messagebox

def generate_fib():
    try:
        n = int(entry.get())
        if n < 0 or n >= 25:
            messagebox.showerror("Error", "Enter n between 0 and 24")
            return

        fib = [0] * 25
        fib[0] = 0
        fib[1] = 1

        for i in range(2, n + 1):
            fib[i] = fib[i - 2] + fib[i - 1]

        output = "\n".join(str(fib[i]) for i in range(n + 1))
        result_label.config(text=output)

    except:
        messagebox.showerror("Error", "Please enter a valid integer")

root = tk.Tk()
root.title("Fibonacci Using Array")
root.geometry("300x350")

tk.Label(root, text="Enter n:").pack(pady=5)

entry = tk.Entry(root)
entry.pack(pady=5)

btn = tk.Button(root, text="Generate Fibonacci", command=generate_fib)
btn.pack(pady=10)

result_label = tk.Label(root, text="", justify="left")
result_label.pack(pady=10)

root.mainloop()
```

---

If you want, I can also give:
👉 Fibonacci using **recursion**
👉 Fibonacci using **loops only**
👉 Fibonacci using **dynamic programming**

Just ask!
