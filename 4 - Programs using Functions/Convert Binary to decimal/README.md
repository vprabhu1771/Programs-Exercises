```
https://www.rapidtables.com/convert/number/binary-to-decimal.html?x=0011
```

Here is the **corrected and complete C program** for converting **binary to decimal** using your function style.

Your code had **two small issues**:

1. `pow()` requires `#include <math.h>`
2. `pow()` returns `double`, so using it repeatedly is unnecessary — but it still works.

Below is the corrected and working code:

---

## ✅ **Corrected C Program (Using Your Function)**

```c
#include <stdio.h>
#include <math.h>

int binary_to_decimal(int n);

int main()
{
    int binary;

    printf("Enter binary number: ");
    scanf("%d", &binary);

    int decimal = binary_to_decimal(binary);

    printf("Decimal: %d\n", decimal);

    return 0;
}

int binary_to_decimal(int n)
{
    int decimal = 0, i = 0, rem;

    while(n != 0)
    {
        rem = n % 10;          // extract last digit
        n = n / 10;            // remove last digit
        decimal += rem * pow(2, i);
        i++;
    }

    return decimal;
}
```

---

## ⭐ Better Version (without pow)

`pow()` is slower and returns `double`. Here is a **faster version** using multiplication:

```c
int binary_to_decimal(int n)
{
    int decimal = 0;
    int base = 1;

    while (n > 0)
    {
        int rem = n % 10;
        decimal += rem * base;
        base *= 2;
        n /= 10;
    }

    return decimal;
}
```

---

If you want, I can also give:

✔ C++ version
✔ Java version
✔ Python version
✔ Tkinter GUI version

Just tell me!

Here are **Binary → Decimal** programs in **C++**, **Java**, and **Python Tkinter GUI** — all clean and working.

---

# ✅ **C++ Program (Binary to Decimal)**

```cpp
#include <iostream>
#include <cmath>
using namespace std;

int binary_to_decimal(long long n) {
    int decimal = 0, i = 0, rem;

    while (n != 0) {
        rem = n % 10;
        n /= 10;
        decimal += rem * pow(2, i);
        i++;
    }
    return decimal;
}

int main() {
    long long binary;
    
    cout << "Enter binary number: ";
    cin >> binary;

    cout << "Decimal: " << binary_to_decimal(binary) << endl;

    return 0;
}
```

---

# ✅ **Java Program (Binary to Decimal)**

```java
import java.util.Scanner;

public class BinaryToDecimal {

    public static int binaryToDecimal(int n) {
        int decimal = 0;
        int base = 1;

        while (n > 0) {
            int rem = n % 10;
            decimal += rem * base;
            base *= 2;
            n = n / 10;
        }

        return decimal;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter binary number: ");
        int binary = sc.nextInt();

        int decimal = binaryToDecimal(binary);

        System.out.println("Decimal: " + decimal);
    }
}
```

---

# ✅ **Python Tkinter GUI (Binary → Decimal Converter)**

```python
import tkinter as tk
from tkinter import messagebox

def convert():
    binary = entry.get()

    # validate binary
    if not all(ch in '01' for ch in binary):
        messagebox.showerror("Error", "Please enter a valid binary number!")
        return

    decimal = int(binary, 2)  # python shortcut

    result_label.config(text=f"Decimal: {decimal}")

# GUI Window
root = tk.Tk()
root.title("Binary to Decimal Converter")
root.geometry("300x200")

title = tk.Label(root, text="Binary to Decimal", font=("Arial", 14, "bold"))
title.pack(pady=10)

entry = tk.Entry(root, font=("Arial", 14), justify="center")
entry.pack(pady=5)

btn = tk.Button(root, text="Convert", font=("Arial", 12), command=convert)
btn.pack(pady=5)

result_label = tk.Label(root, text="Decimal: ", font=("Arial", 14))
result_label.pack(pady=10)

root.mainloop()
```

---

If you want, I can also give:

✔ Tkinter version with live typing
✔ Tkinter version with dark mode
✔ A full desktop app (binary ↔ decimal ↔ octal ↔ hex)

Just tell me!
