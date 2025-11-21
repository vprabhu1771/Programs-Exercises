```c
#include<stdio.h>
#include<conio.h>

void main()
{
    int n, i;
    
    printf("Enter an integer to find multiplication table: ");
    scanf("%d", &n);
    
    for(i=1; i<=20;i++){
        printf("%d * %d = %d\n", n, i, n*i);
    }
    
    getch();
}
```

Here’s your **Multiplication Table program** in **C**, **C++**, **Java**, **Python**, and **Tkinter GUI** — ready to run.

---

# ✅ **C (Turbo C style with conio.h)**

```c
#include <stdio.h>
#include <conio.h>

void main()
{
    int n, i;
    
    clrscr();

    printf("Enter an integer to find multiplication table: ");
    scanf("%d", &n);
    
    for(i = 1; i <= 20; i++){
        printf("%d * %d = %d\n", n, i, n * i);
    }
    
    getch();
}
```

---

# ✅ **C++ Version**

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter an integer to find multiplication table: ";
    cin >> n;

    for(int i = 1; i <= 20; i++) {
        cout << n << " * " << i << " = " << n * i << endl;
    }

    return 0;
}
```

---

# ✅ **Java Version**

```java
import java.util.Scanner;

public class MultiplicationTable {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter an integer to find multiplication table: ");
        int n = sc.nextInt();

        for(int i = 1; i <= 20; i++) {
            System.out.println(n + " * " + i + " = " + (n * i));
        }
    }
}
```

---

# ✅ **Python Version**

```python
n = int(input("Enter an integer to find multiplication table: "))

for i in range(1, 21):
    print(f"{n} * {i} = {n*i}")
```

---

# ✅ **Tkinter GUI Version (Python)**

```python
import tkinter as tk

def show_table():
    output.delete("1.0", tk.END)
    n = int(entry.get())
    for i in range(1, 21):
        output.insert(tk.END, f"{n} * {i} = {n*i}\n")

root = tk.Tk()
root.title("Multiplication Table")

tk.Label(root, text="Enter a number:").pack()
entry = tk.Entry(root)
entry.pack()

tk.Button(root, text="Show Table", command=show_table).pack()

output = tk.Text(root, height=22, width=25)
output.pack()

root.mainloop()
```

---

I can also make a **Tkinter version with:**

* Customizable table range (not just 1–20)
* Colorful UI for better readability

Do you want me to create that?
