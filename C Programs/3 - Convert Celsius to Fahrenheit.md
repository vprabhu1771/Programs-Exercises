Here are the **C, C++, Java, Python (Console), and Python Tkinter GUI** versions for converting **Celsius to Fahrenheit**.

---

# ✅ **1. C Program**

```c
#include <stdio.h>

int main() {
    float celsius, fahrenheit;

    printf("Enter Temperature in Celsius: ");
    scanf("%f", &celsius);

    fahrenheit = (1.8 * celsius) + 32;

    printf("Temperature in Fahrenheit: %.2f\n", fahrenheit);

    return 0;
}
```

---

# ✅ **2. C++ Program**

```cpp
#include <iostream>
using namespace std;

int main() {
    float celsius, fahrenheit;

    cout << "Enter Temperature in Celsius: ";
    cin >> celsius;

    fahrenheit = (1.8 * celsius) + 32;

    cout << "Temperature in Fahrenheit: " << fahrenheit << endl;

    return 0;
}
```

---

# ✅ **3. Java Program**

```java
import java.util.Scanner;

public class CelsiusToFahrenheit {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Temperature in Celsius: ");
        float celsius = sc.nextFloat();

        float fahrenheit = (1.8f * celsius) + 32;

        System.out.println("Temperature in Fahrenheit: " + fahrenheit);
    }
}
```

---

# ✅ **4. Python Program (Console)**

```python
celsius = float(input("Enter Temperature in Celsius: "))

fahrenheit = (1.8 * celsius) + 32

print("Temperature in Fahrenheit:", fahrenheit)
```

---

# ✅ **5. Python Tkinter GUI Program**

```python
import tkinter as tk

def convert():
    try:
        c = float(entry.get())
        f = (1.8 * c) + 32
        result_label.config(text=f"Fahrenheit: {f:.2f}")
    except ValueError:
        result_label.config(text="Invalid Input!")

root = tk.Tk()
root.title("Celsius to Fahrenheit Converter")
root.geometry("300x150")

label = tk.Label(root, text="Enter Celsius:")
label.pack(pady=5)

entry = tk.Entry(root)
entry.pack(pady=5)

button = tk.Button(root, text="Convert", command=convert)
button.pack(pady=5)

result_label = tk.Label(root, text="Fahrenheit: ")
result_label.pack(pady=5)

root.mainloop()
```

---

If you want **Fahrenheit → Celsius** also, or want a **Tkinter app with two-way conversion**, tell me!
