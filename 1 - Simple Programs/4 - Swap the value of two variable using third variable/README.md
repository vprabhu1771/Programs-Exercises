# C

```c
#include<stdio.h>

void main()
{
	float a, b, temp;

	printf("Enter a value\n");

	scanf("%f", &a);

	printf("Enter b value\n");

	scanf("%f", &b);

	temp = a;

	a = b;

	b = temp;

	printf("a = %f\n", a);	

	printf("b = %f\n", b);
}
```

# CPP

```cpp
#include<iostream>

using namespace std;

void main()
{
	float a, b, temp;

	cout << "Enter a value" << endl;

	cin >> a;

	cout << "Enter b value" << endl;

	cin >> b;

	temp = a;

	a = b;

	b = temp;

	cout << "a = " << a << endl;

	cout << "b = " << b << endl;
}
```

Here are the **same “swap two numbers” programs** in **Java**, **Python**, and **Tkinter GUI (Python)**.

---

# ✅ **Java Version**

```java
import java.util.Scanner;

public class SwapNumbers {
    public static void main(String[] args) {

        float a, b, temp;
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter a value:");
        a = sc.nextFloat();

        System.out.println("Enter b value:");
        b = sc.nextFloat();

        temp = a;
        a = b;
        b = temp;

        System.out.println("a = " + a);
        System.out.println("b = " + b);
    }
}
```

---

# ✅ **Python Version**

```python
a = float(input("Enter a value: "))
b = float(input("Enter b value: "))

temp = a
a = b
b = temp

print("a =", a)
print("b =", b)
```

---

# ✅ **Tkinter GUI Version (Python)**

A small GUI window with two input fields and a swap button.

```python
import tkinter as tk
from tkinter import messagebox

def swap_numbers():
    try:
        a = float(entry_a.get())
        b = float(entry_b.get())

        a, b = b, a  # swap

        entry_a.delete(0, tk.END)
        entry_a.insert(0, str(a))

        entry_b.delete(0, tk.END)
        entry_b.insert(0, str(b))

    except ValueError:
        messagebox.showerror("Error", "Please enter valid numbers")

root = tk.Tk()
root.title("Swap Two Numbers")

tk.Label(root, text="Enter a value:").grid(row=0, column=0, padx=10, pady=5)
entry_a = tk.Entry(root)
entry_a.grid(row=0, column=1)

tk.Label(root, text="Enter b value:").grid(row=1, column=0, padx=10, pady=5)
entry_b = tk.Entry(root)
entry_b.grid(row=1, column=1)

swap_button = tk.Button(root, text="Swap", command=swap_numbers)
swap_button.grid(row=2, column=0, columnspan=2, pady=10)

root.mainloop()
```

---

If you want, I can also give:

✅ C#,
✅ C++ GUI using Qt,
✅ Java Swing GUI,
✅ Flutter UI version.

Just tell me!
