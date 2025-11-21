```c
#include<stdio.h>
#include<conio.h>

void main()
{
    int base, exp;
    
    long long int value = 1;
    
    printf("Enter base number and exponent seperated by spaces..\n");
    scanf("%d%d", &base, &exp);
    
    while(exp!=0){
        value*=base;
        --exp;
    }
    printf("The answer is %lld", value);
    
    getch();
}
```

Here’s your **Power Calculation program** (base^exponent) in **C**, **C++**, **Java**, **Python**, and **Tkinter GUI**. I’ve corrected formatting and used proper types for large numbers.

---

# ✅ **C (Turbo C style with conio.h)**

```c
#include <stdio.h>
#include <conio.h>

void main()
{
    int base, exp;
    long long int value = 1;

    clrscr();

    printf("Enter base and exponent separated by spaces: ");
    scanf("%d %d", &base, &exp);

    while(exp != 0) {
        value *= base;
        --exp;
    }

    printf("The answer is %lld", value);

    getch();
}
```

---

# ✅ **C++ Version**

```cpp
#include <iostream>
using namespace std;

int main() {
    int base, exp;
    long long value = 1;

    cout << "Enter base and exponent separated by spaces: ";
    cin >> base >> exp;

    while(exp != 0) {
        value *= base;
        --exp;
    }

    cout << "The answer is " << value;
    return 0;
}
```

---

# ✅ **Java Version**

```java
import java.util.Scanner;

public class PowerCalculator {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter base and exponent separated by spaces: ");
        int base = sc.nextInt();
        int exp = sc.nextInt();

        long value = 1;

        while(exp != 0) {
            value *= base;
            exp--;
        }

        System.out.println("The answer is " + value);
    }
}
```

---

# ✅ **Python Version**

```python
base, exp = map(int, input("Enter base and exponent separated by spaces: ").split())
value = 1

while exp != 0:
    value *= base
    exp -= 1

print(f"The answer is {value}")
```

*Alternatively, in Python you can use the built-in operator `**`:*

```python
base, exp = map(int, input("Enter base and exponent separated by spaces: ").split())
value = base ** exp
print(f"The answer is {value}")
```

---

# ✅ **Tkinter GUI Version (Python)**

```python
import tkinter as tk

def calculate_power():
    base = int(base_entry.get())
    exp = int(exp_entry.get())
    value = 1
    temp = exp
    while temp != 0:
        value *= base
        temp -= 1
    result.config(text=f"The answer is {value}")

root = tk.Tk()
root.title("Power Calculator")

tk.Label(root, text="Base:").pack()
base_entry = tk.Entry(root)
base_entry.pack()

tk.Label(root, text="Exponent:").pack()
exp_entry = tk.Entry(root)
exp_entry.pack()

tk.Button(root, text="Calculate", command=calculate_power).pack()

result = tk.Label(root, text="")
result.pack()

root.mainloop()
```

---

If you want, I can make an **improved Tkinter version** with:

* **Supports negative exponents**
* **Supports decimal bases**
* **Dynamic error handling**

Do you want me to do that?
