```c
#include<stdio.h>
#include<conio.h>
#include<math.h>

void main()
{
    int i, n, factorial;
    
    printf("Enter any number: ");
    scanf("%d",&n);
    
    factorial = 1;
    for(i=1; i<=n; i++){
        factorial = factorial * i;
        
    }
    printf("Factorial of %d is %d", n, factorial);
    
    getch();
}
```

Here are **correct factorial programs** in **C**, **C++**, **Java**, **Python**, and **Tkinter GUI** — all clean and working.

---

# ✅ **C Program (Turbo C style with conio.h)**

```c
#include<stdio.h>
#include<conio.h>

void main()
{
    int i, n, factorial = 1;

    clrscr();

    printf("Enter any number: ");
    scanf("%d",&n);

    for(i = 1; i <= n; i++){
        factorial = factorial * i;
    }

    printf("Factorial of %d is %d", n, factorial);

    getch();
}
```

---

# ✅ **C++ Version**

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, fact = 1;
    cout << "Enter any number: ";
    cin >> n;

    for(int i = 1; i <= n; i++) {
        fact *= i;
    }

    cout << "Factorial of " << n << " is " << fact;
    return 0;
}
```

---

# ✅ **Java Version**

```java
import java.util.Scanner;

public class Factorial {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter any number: ");
        int n = sc.nextInt();

        int fact = 1;
        for (int i = 1; i <= n; i++) {
            fact *= i;
        }

        System.out.println("Factorial of " + n + " is " + fact);
    }
}
```

---

# ✅ **Python Version**

```python
n = int(input("Enter any number: "))
fact = 1

for i in range(1, n+1):
    fact *= i

print(f"Factorial of {n} is {fact}")
```

---

# ✅ **Tkinter GUI Version (Python)**

```python
import tkinter as tk

def find_factorial():
    n = int(entry.get())
    fact = 1
    for i in range(1, n+1):
        fact *= i
    result.config(text=f"Factorial of {n} is {fact}")

root = tk.Tk()
root.title("Factorial Calculator")

tk.Label(root, text="Enter a number:").pack()

entry = tk.Entry(root)
entry.pack()

tk.Button(root, text="Calculate", command=find_factorial).pack()

result = tk.Label(root, text="")
result.pack()

root.mainloop()
```

---

If you want, I can also give:

✅ **Recursive factorial** versions
✅ **Tkinter advanced UI**
✅ **Factorial using BigInt for large numbers** (Java/Python/C++)

Just ask!
