# C

```c
#include<stdio.h>
#include<conio.h>

void main()
{
    float num;
    
    printf("Enter any number: ");
    scanf("%f",&num);
    
    if(num == 0){
        printf("%.2f is either positive nor negative", num);
    }
    else if(num > 0){
        printf("%.2f is positive",num);
    }
    else{
        printf("%.2f is negative", num);
    }
    
    getch();    
}
```

Here are the same **“positive, negative, or zero check”** programs written in **C++**, **Java**, **Python**, and **Tkinter (Python GUI)**.

---

# ✅ **C++ Version**

```cpp
#include <iostream>
using namespace std;

int main() {
    float num;

    cout << "Enter any number: ";
    cin >> num;

    if (num == 0) {
        cout << num << " is neither positive nor negative";
    }
    else if (num > 0) {
        cout << num << " is positive";
    }
    else {
        cout << num << " is negative";
    }

    return 0;
}
```

---

# ✅ **Java Version**

```java
import java.util.Scanner;

public class NumberCheck {
    public static void main(String[] args) {

        float num;
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter any number: ");
        num = sc.nextFloat();

        if (num == 0) {
            System.out.println(num + " is neither positive nor negative");
        }
        else if (num > 0) {
            System.out.println(num + " is positive");
        }
        else {
            System.out.println(num + " is negative");
        }
    }
}
```

---

# ✅ **Python Version**

```python
num = float(input("Enter any number: "))

if num == 0:
    print(f"{num} is neither positive nor negative")
elif num > 0:
    print(f"{num} is positive")
else:
    print(f"{num} is negative")
```

---

# ✅ **Tkinter GUI Version (Python)**

A simple GUI app to check whether a number is positive, negative, or zero.

```python
import tkinter as tk
from tkinter import messagebox

def check_number():
    try:
        num = float(entry.get())

        if num == 0:
            result = f"{num} is neither positive nor negative"
        elif num > 0:
            result = f"{num} is positive"
        else:
            result = f"{num} is negative"

        messagebox.showinfo("Result", result)

    except ValueError:
        messagebox.showerror("Error", "Please enter a valid number")

root = tk.Tk()
root.title("Number Check")

tk.Label(root, text="Enter any number:").grid(row=0, column=0, padx=10, pady=10)

entry = tk.Entry(root)
entry.grid(row=0, column=1, padx=10)

btn = tk.Button(root, text="Check", command=check_number)
btn.grid(row=1, column=0, columnspan=2, pady=10)

root.mainloop()
```

---

If you want next:

✔ C version
✔ Java Swing version
✔ Flutter simple UI version

Just tell me!
