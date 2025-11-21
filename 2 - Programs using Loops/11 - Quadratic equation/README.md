```c
#include<stdio.h>
#include<conio.h>
#include<math.h>

void main()
{
    int a, b, c;
    
    float x, y, z;
    
    clrscr();
    
    printf("Enter values of a, b, c seperated by spaces..\n");
    scanf("%d%d%d",&a,&b,&c);
    
    x = ((b*b) - (4*a*c));
    
    if(x>0){
        printf("Roots are real \n");
        y = -b+sqrt(x)/2*a;
        z = -b-sqrt(x)/2*a;
        
        printf("The roots are %f, %f",y, z);
    }
    else if(x<0){
        printf("The roots are imaginary");
    }
    else{
        printf("Roots are real and equal\n");
        y = ((-b)+sqrt(x))/(2*a);
        z = ((-b)-sqrt(x))/(2*a);
        printf("the roots are %f, %f \n",y,z);
    }
    
    getch();
}
```

Below is the **correct formula**, and then full working code for **C (Turbo C style)**, **C modern**, **C++**, **Java**, **Python**, and **Tkinter GUI**.

---

# ✅ **Correct Formula**

The quadratic equation is:

```
ax² + bx + c = 0
```

Discriminant:

```
D = b² − 4ac
```

Roots:

```
x1 = (-b + √D) / (2a)
x2 = (-b − √D) / (2a)
```

⚠️ Your code mistake:

```
y = -b+sqrt(x)/2*a;   // WRONG
z = -b-sqrt(x)/2*a;   // WRONG
```

Because `/` has higher precedence than `*` — it becomes:

```
-b + (sqrt(x)/2)*a   // WRONG mathematics
```

---

# ✅ **Fixed C Code (Turbo C style — using conio.h)**

```c
#include <stdio.h>
#include <conio.h>
#include <math.h>

void main()
{
    int a, b, c;
    float d, x1, x2;

    clrscr();

    printf("Enter a, b, c: ");
    scanf("%d %d %d", &a, &b, &c);

    d = (b * b) - (4 * a * c);

    if (d > 0) {
        printf("Roots are real and distinct\n");
        x1 = (-b + sqrt(d)) / (2 * a);
        x2 = (-b - sqrt(d)) / (2 * a);
        printf("Roots: %f , %f", x1, x2);
    }
    else if (d == 0) {
        printf("Roots are real and equal\n");
        x1 = x2 = -b / (2 * a);
        printf("Root: %f", x1);
    }
    else {
        printf("Roots are imaginary");
    }

    getch();
}
```

---

# ✅ **Modern C (without conio.h)**

```c
#include <stdio.h>
#include <math.h>

int main() {
    int a, b, c;
    float d, x1, x2;

    printf("Enter a, b, c: ");
    scanf("%d %d %d", &a, &b, &c);

    d = b*b - 4*a*c;

    if (d > 0) {
        x1 = (-b + sqrt(d)) / (2*a);
        x2 = (-b - sqrt(d)) / (2*a);
        printf("Roots: %.2f, %.2f\n", x1, x2);
    }
    else if (d == 0) {
        x1 = -b / (2*a);
        printf("Roots equal: %.2f\n", x1);
    }
    else {
        printf("Imaginary roots\n");
    }

    return 0;
}
```

---

# ✅ **C++ Version**

```cpp
#include <iostream>
#include <cmath>
using namespace std;

int main() {
    int a, b, c;
    cout << "Enter a, b, c: ";
    cin >> a >> b >> c;

    float d = b*b - 4*a*c;

    if (d > 0) {
        float x1 = (-b + sqrt(d)) / (2*a);
        float x2 = (-b - sqrt(d)) / (2*a);
        cout << "Roots: " << x1 << ", " << x2;
    }
    else if (d == 0) {
        float x = -b / (2*a);
        cout << "Equal roots: " << x;
    }
    else {
        cout << "Imaginary roots";
    }
}
```

---

# ✅ **Java Version**

```java
import java.util.Scanner;

public class Quadratic {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a, b, c: ");
        int a = sc.nextInt();
        int b = sc.nextInt();
        int c = sc.nextInt();

        double d = b*b - 4*a*c;

        if (d > 0) {
            double x1 = (-b + Math.sqrt(d)) / (2 * a);
            double x2 = (-b - Math.sqrt(d)) / (2 * a);
            System.out.println("Roots: " + x1 + ", " + x2);
        }
        else if (d == 0) {
            double x = -b / (2.0 * a);
            System.out.println("Equal Roots: " + x);
        }
        else {
            System.out.println("Imaginary roots");
        }
    }
}
```

---

# ✅ **Python Version**

```python
import math

a = int(input("Enter a: "))
b = int(input("Enter b: "))
c = int(input("Enter c: "))

d = b*b - 4*a*c

if d > 0:
    x1 = (-b + math.sqrt(d)) / (2*a)
    x2 = (-b - math.sqrt(d)) / (2*a)
    print("Roots:", x1, x2)

elif d == 0:
    x = -b / (2*a)
    print("Roots equal:", x)

else:
    print("Imaginary roots")
```

---

# ✅ **Tkinter GUI Version (Python)**

```python
import tkinter as tk
import math

def solve():
    a = float(a_entry.get())
    b = float(b_entry.get())
    c = float(c_entry.get())
    
    d = b*b - 4*a*c
    
    if d > 0:
        x1 = (-b + math.sqrt(d)) / (2*a)
        x2 = (-b - math.sqrt(d)) / (2*a)
        result.config(text=f"Real Roots:\n{x1}\n{x2}")
    elif d == 0:
        x = -b / (2*a)
        result.config(text=f"Equal Roots:\n{x}")
    else:
        result.config(text="Imaginary Roots")

root = tk.Tk()
root.title("Quadratic Equation Solver")

tk.Label(root, text="a").pack()
a_entry = tk.Entry(root)
a_entry.pack()

tk.Label(root, text="b").pack()
b_entry = tk.Entry(root)
b_entry.pack()

tk.Label(root, text="c").pack()
c_entry = tk.Entry(root)
c_entry.pack()

tk.Button(root, text="Solve", command=solve).pack()

result = tk.Label(root, text="")
result.pack()

root.mainloop()
```

---

# If you want:

✅ Tkinter with better UI
✅ Tkinter image background
✅ C++ GUI (Qt)
✅ Java Swing GUI

Just tell me — I can generate.
