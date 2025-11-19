# ✅ **C Version**

```c
#include<stdio.h>
#include<conio.h>

void main()
{
    float n1, n2, n3;
    
    printf("Enter three numbers seperated by spaces:  ");
    scanf("%f %f %f", &n1, &n2, &n3);
    
    if(n1 > n2 && n1 > n3){
        printf("%.2f is greater",n1);
    }
    else if(n2 > n1 && n2 > n3){
        printf("%.2f is greater",n2);
    }
    else{
        printf("%.2f is greater",n3);
    }
    
    getch(); 
}
```

Here are the same **“find the largest of three numbers”** programs written in **C++**, **Java**, **Python**, and **Tkinter (Python GUI)**.

---

# ✅ **C++ Version**

```cpp
#include <iostream>
using namespace std;

int main() {
    float n1, n2, n3;

    cout << "Enter three numbers separated by spaces: ";
    cin >> n1 >> n2 >> n3;

    if (n1 > n2 && n1 > n3) {
        cout << n1 << " is greater";
    }
    else if (n2 > n1 && n2 > n3) {
        cout << n2 << " is greater";
    }
    else {
        cout << n3 << " is greater";
    }

    return 0;
}
```

---

# ✅ **Java Version**

```java
import java.util.Scanner;

public class LargestNumber {
    public static void main(String[] args) {
        float n1, n2, n3;

        Scanner sc = new Scanner(System.in);
        System.out.print("Enter three numbers separated by spaces: ");

        n1 = sc.nextFloat();
        n2 = sc.nextFloat();
        n3 = sc.nextFloat();

        if (n1 > n2 && n1 > n3) {
            System.out.println(n1 + " is greater");
        } else if (n2 > n1 && n2 > n3) {
            System.out.println(n2 + " is greater");
        } else {
            System.out.println(n3 + " is greater");
        }
    }
}
```

---

# ✅ **Python Version**

```python
n1, n2, n3 = map(float, input("Enter three numbers separated by spaces: ").split())

if n1 > n2 and n1 > n3:
    print(f"{n1} is greater")
elif n2 > n1 and n2 > n3:
    print(f"{n2} is greater")
else:
    print(f"{n3} is greater")
```

---

# ✅ **Tkinter GUI Version (Python)**

A simple GUI to enter 3 numbers and find the largest.

```python
import tkinter as tk
from tkinter import messagebox

def find_largest():
    try:
        n1 = float(entry1.get())
        n2 = float(entry2.get())
        n3 = float(entry3.get())

        if n1 > n2 and n1 > n3:
            result = f"{n1} is greater"
        elif n2 > n1 and n2 > n3:
            result = f"{n2} is greater"
        else:
            result = f"{n3} is greater"

        messagebox.showinfo("Result", result)

    except ValueError:
        messagebox.showerror("Error", "Please enter valid numbers")

root = tk.Tk()
root.title("Largest of Three Numbers")

tk.Label(root, text="Enter n1:").grid(row=0, column=0, padx=10, pady=5)
entry1 = tk.Entry(root)
entry1.grid(row=0, column=1)

tk.Label(root, text="Enter n2:").grid(row=1, column=0, padx=10, pady=5)
entry2 = tk.Entry(root)
entry2.grid(row=1, column=1)

tk.Label(root, text="Enter n3:").grid(row=2, column=0, padx=10, pady=5)
entry3 = tk.Entry(root)
entry3.grid(row=2, column=1)

btn = tk.Button(root, text="Find Greatest", command=find_largest)
btn.grid(row=3, column=0, columnspan=2, pady=10)

root.mainloop()
```

---

If you want, I can also provide:

✅ C# WinForms
✅ Java Swing
✅ Flutter UI
Just tell me!
