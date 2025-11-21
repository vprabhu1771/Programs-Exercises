```c
#include<stdio.h>
#include<conio.h>
void main()
{
    int n;
    
    puts("Not squaren");
    puts("-------------------");
    
    for (n=1; n<=10; n++){
        printf("%d\t%d\n",n,n*n);
    }    
    getch();
}
```
Here’s your **“Number and Square” program** in **C**, **C++**, **Java**, **Python**, and **Tkinter GUI** with the same logic. I’ve fixed minor formatting for clarity.

---

# ✅ **C (Turbo C style with conio.h)**

```c
#include <stdio.h>
#include <conio.h>

void main()
{
    int n;
    
    puts("Number\tSquare");
    puts("-------------------");
    
    for (n = 1; n <= 10; n++) {
        printf("%d\t%d\n", n, n * n);
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
    cout << "Number\tSquare" << endl;
    cout << "-------------------" << endl;

    for(int n = 1; n <= 10; n++) {
        cout << n << "\t" << n*n << endl;
    }

    return 0;
}
```

---

# ✅ **Java Version**

```java
public class NumberSquare {
    public static void main(String[] args) {
        System.out.println("Number\tSquare");
        System.out.println("-------------------");

        for(int n = 1; n <= 10; n++) {
            System.out.println(n + "\t" + (n*n));
        }
    }
}
```

---

# ✅ **Python Version**

```python
print("Number\tSquare")
print("-------------------")

for n in range(1, 11):
    print(f"{n}\t{n*n}")
```

---

# ✅ **Tkinter GUI Version (Python)**

```python
import tkinter as tk

def show_squares():
    output.delete("1.0", tk.END)
    output.insert(tk.END, "Number\tSquare\n")
    output.insert(tk.END, "-------------------\n")
    for n in range(1, 11):
        output.insert(tk.END, f"{n}\t{n*n}\n")

root = tk.Tk()
root.title("Number and Square")

tk.Button(root, text="Show Squares", command=show_squares).pack()

output = tk.Text(root, height=12, width=20)
output.pack()

root.mainloop()
```

---

If you want, I can also make a **Tkinter version with a dynamic input** so the user can enter **any range** instead of 1–10. Do you want me to do that?
