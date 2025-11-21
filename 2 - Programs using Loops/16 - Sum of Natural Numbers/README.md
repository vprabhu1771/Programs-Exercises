```c
#include<stdio.h>
#include<conio.h>

void main()
{
    int n, count, sum = 0;
    
    printf("Enter an integer: ");
    scanf("%d", &n);
    
    count = 1;
    while( count <= n){
        sum += count;
        ++count;
    }
    printf("Sum = %d", sum);
    getch();
}
```

Here’s your **Sum of first N numbers program** in **C**, **C++**, **Java**, **Python**, and **Tkinter GUI**.

---

# ✅ **C (Turbo C style with conio.h)**

```c
#include <stdio.h>
#include <conio.h>

void main()
{
    int n, count, sum = 0;
    
    clrscr();

    printf("Enter an integer: ");
    scanf("%d", &n);
    
    count = 1;
    while(count <= n){
        sum += count;
        ++count;
    }

    printf("Sum = %d", sum);
    
    getch();
}
```

---

# ✅ **C++ Version**

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, sum = 0, count = 1;

    cout << "Enter an integer: ";
    cin >> n;

    while(count <= n){
        sum += count;
        count++;
    }

    cout << "Sum = " << sum;
    return 0;
}
```

---

# ✅ **Java Version**

```java
import java.util.Scanner;

public class SumOfN {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter an integer: ");
        int n = sc.nextInt();

        int sum = 0, count = 1;
        while(count <= n){
            sum += count;
            count++;
        }

        System.out.println("Sum = " + sum);
    }
}
```

---

# ✅ **Python Version**

```python
n = int(input("Enter an integer: "))
sum = 0
count = 1

while count <= n:
    sum += count
    count += 1

print(f"Sum = {sum}")
```

*Alternative using formula:*

```python
n = int(input("Enter an integer: "))
sum = n * (n + 1) // 2
print(f"Sum = {sum}")
```

---

# ✅ **Tkinter GUI Version (Python)**

```python
import tkinter as tk

def calculate_sum():
    n = int(entry.get())
    sum = 0
    count = 1
    while count <= n:
        sum += count
        count += 1
    result.config(text=f"Sum = {sum}")

root = tk.Tk()
root.title("Sum of First N Numbers")

tk.Label(root, text="Enter an integer:").pack()
entry = tk.Entry(root)
entry.pack()

tk.Button(root, text="Calculate Sum", command=calculate_sum).pack()

result = tk.Label(root, text="")
result.pack()

root.mainloop()
```

---

I can also create a **Tkinter version with optional “formula method”** for faster calculation and dynamic input validation if you want.

Do you want me to do that?
