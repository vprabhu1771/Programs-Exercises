Your current logic is **not correct** for detecting leap years or century years.
Let’s break the rules first:

### ✅ Leap Year Rules

A year is a leap year if:
1️⃣ Divisible by 400 → **Leap Year**
2️⃣ Divisible by 100 but not 400 → **Century but Not a Leap Year**
3️⃣ Divisible by 4 but not 100 → **Leap Year**
Else → **Not a Leap Year**

---

### ✔ Corrected C Program

```c
#include <stdio.h>

int main() {
    int year;

    printf("Enter a year: ");
    scanf("%d", &year);

    if (year % 400 == 0) {
        printf("%d is a leap year (century leap year)", year);
    }
    else if (year % 100 == 0) {
        printf("%d is a century year but not a leap year", year);
    }
    else if (year % 4 == 0) {
        printf("%d is a leap year", year);
    }
    else {
        printf("%d is not a leap year", year);
    }

    return 0;
}
```

---

### 📌 Example Outputs

| Input year | Output                                     |
| ---------- | ------------------------------------------ |
| 2000       | 2000 is a leap year (century leap year)    |
| 1900       | 1900 is a century year but not a leap year |
| 2024       | 2024 is a leap year                        |
| 2023       | 2023 is not a leap year                    |

---

If you want, I can also show:
✔ Version with `else if` simplified
✔ Only check leap year without century message
✔ Switch-case style (conceptual)

Would you like any of those versions?

# C

```c
#include<stdio.h>
#include<conio.h>

void main()
{
    int year;
    
    printf("Enter a year: ");
    scanf("%d",&year);
    
    if(year % 4 == 0){
        printf("%d is a leap year", year);
    }
    else if(year % 100 == 0){
        printf("%d is a century year", year);
    }
    else{
        printf("%d is not a leap year", year);
    }
    
    getch();  
}
```

Below are the same **“Leap Year Checker”** programs written in **C++**, **Java**, **Python**, and **Tkinter (Python GUI)**.

---

# ✅ **C++ Version**

```cpp
#include <iostream>
using namespace std;

int main() {
    int year;

    cout << "Enter a year: ";
    cin >> year;

    if (year % 4 == 0) {
        cout << year << " is a leap year";
    }
    else if (year % 100 == 0) {
        cout << year << " is a century year";
    }
    else {
        cout << year << " is not a leap year";
    }

    return 0;
}
```

---

# ✅ **Java Version**

```java
import java.util.Scanner;

public class LeapYear {
    public static void main(String[] args) {

        int year;
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a year: ");
        year = sc.nextInt();

        if (year % 4 == 0) {
            System.out.println(year + " is a leap year");
        }
        else if (year % 100 == 0) {
            System.out.println(year + " is a century year");
        }
        else {
            System.out.println(year + " is not a leap year");
        }
    }
}
```

---

# ✅ **Python Version**

```python
year = int(input("Enter a year: "))

if year % 4 == 0:
    print(f"{year} is a leap year")
elif year % 100 == 0:
    print(f"{year} is a century year")
else:
    print(f"{year} is not a leap year")
```

---

# ✅ **Tkinter GUI Version (Python)**

A simple GUI to check leap year.

```python
import tkinter as tk
from tkinter import messagebox

def check_year():
    try:
        year = int(entry.get())

        if year % 4 == 0:
            result = f"{year} is a leap year"
        elif year % 100 == 0:
            result = f"{year} is a century year"
        else:
            result = f"{year} is not a leap year"

        messagebox.showinfo("Result", result)

    except ValueError:
        messagebox.showerror("Error", "Please enter a valid year")

root = tk.Tk()
root.title("Leap Year Checker")

tk.Label(root, text="Enter a year:").grid(row=0, column=0, padx=10, pady=10)

entry = tk.Entry(root)
entry.grid(row=0, column=1, padx=10)

btn = tk.Button(root, text="Check", command=check_year)
btn.grid(row=1, column=0, columnspan=2, pady=10)

root.mainloop()
```

---

If you want, I can also give you:

✅ Correct leap year logic (full rule: divisible by 400)
✅ Java Swing version
✅ C# WinForms version

Just tell me!
