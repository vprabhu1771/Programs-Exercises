Here are **decimal to binary** programs in **C, C++, Java, Python**, and a **Tkinter GUI** version.

---

# ✅ **C Program – Decimal to Binary**

```c
#include <stdio.h>

int decimal_to_binary(int n) {
    int binary = 0, base = 1, rem;

    while (n > 0) {
        rem = n % 2;
        binary = binary + rem * base;
        base = base * 10;
        n = n / 2;
    }

    return binary;
}

int main() {
    int num;
    printf("Enter decimal number: ");
    scanf("%d", &num);

    printf("Binary: %d\n", decimal_to_binary(num));
    return 0;
}
```

---

# ✅ **C++ Program – Decimal to Binary**

```cpp
#include <iostream>
using namespace std;

int decimal_to_binary(int n) {
    int binary = 0, base = 1;

    while (n > 0) {
        int rem = n % 2;
        binary += rem * base;
        base *= 10;
        n /= 2;
    }

    return binary;
}

int main() {
    int num;
    cout << "Enter decimal number: ";
    cin >> num;

    cout << "Binary: " << decimal_to_binary(num) << endl;
    return 0;
}
```

---

# ✅ **Java Program – Decimal to Binary**

```java
import java.util.Scanner;

public class Main {
    public static int decimal_to_binary(int n) {
        int binary = 0, base = 1;

        while (n > 0) {
            int rem = n % 2;
            binary += rem * base;
            base *= 10;
            n /= 2;
        }
        return binary;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter decimal number: ");
        int num = sc.nextInt();

        System.out.println("Binary: " + decimal_to_binary(num));
    }
}
```

---

# ✅ **Python Program – Decimal to Binary**

```python
def decimal_to_binary(n):
    binary = ""
    while n > 0:
        binary = str(n % 2) + binary
        n //= 2
    return binary

num = int(input("Enter decimal number: "))
print("Binary:", decimal_to_binary(num))
```

---

# ✅ **Tkinter App – Decimal to Binary Converter**

```python
import tkinter as tk

def convert():
    try:
        n = int(entry.get())
        binary = ""
        temp = n
        if temp == 0:
            binary = "0"
        else:
            while temp > 0:
                binary = str(temp % 2) + binary
                temp //= 2
        result_label.config(text=f"Binary: {binary}")
    except:
        result_label.config(text="Invalid Input")

root = tk.Tk()
root.title("Decimal to Binary Converter")
root.geometry("300x200")

tk.Label(root, text="Enter Decimal Number:").pack(pady=5)
entry = tk.Entry(root)
entry.pack(pady=5)

tk.Button(root, text="Convert", command=convert).pack(pady=5)
result_label = tk.Label(root, text="Binary: ")
result_label.pack(pady=10)

root.mainloop()
```

---

If you want, I can also give **binary to decimal**, **hexadecimal**, or a **full Tkinter calculator**.
