# C

```c
#include<stdio.h>

int main()
{
	int num;

	printf("Enter any integer\n");

	scanf("%d", &num);

	if( (num%2) == 0 )
	{
		printf("%d is even\n", num);
	}
	else
	{
		printf("%d is odd\n", num);
	}

	return 0;
}
```

# CPP

```cpp
#include<iostream>

using namespace std;

int main()
{
	int num;

	cout << "Enter any integer" << endl;

	cin >> num;

	if( (num%2) == 0 )
	{		
		cout << num << " is even" << endl;
	}
	else
	{
		cout << num << " is odd" << endl;
	}

	return 0;
}
```
Here are the **same “odd/even check” programs** in **Java**, **Python**, and **Tkinter (Python GUI)**.

---

# ✅ **Java Version**

```java
import java.util.Scanner;

public class OddEven {
    public static void main(String[] args) {

        int num;
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter any integer:");
        num = sc.nextInt();

        if (num % 2 == 0) {
            System.out.println(num + " is even");
        } else {
            System.out.println(num + " is odd");
        }
    }
}
```

---

# ✅ **Python Version**

```python
num = int(input("Enter any integer: "))

if num % 2 == 0:
    print(f"{num} is even")
else:
    print(f"{num} is odd")
```

---

# ✅ **Tkinter GUI Version (Python)**

A simple GUI app that checks whether a number is odd or even.

```python
import tkinter as tk
from tkinter import messagebox

def check_number():
    try:
        num = int(entry_num.get())

        if num % 2 == 0:
            result = f"{num} is even"
        else:
            result = f"{num} is odd"

        messagebox.showinfo("Result", result)

    except ValueError:
        messagebox.showerror("Error", "Please enter a valid integer")

root = tk.Tk()
root.title("Odd or Even Checker")

tk.Label(root, text="Enter an integer:").grid(row=0, column=0, padx=10, pady=10)

entry_num = tk.Entry(root)
entry_num.grid(row=0, column=1, padx=10)

btn = tk.Button(root, text="Check", command=check_number)
btn.grid(row=1, column=0, columnspan=2, pady=10)

root.mainloop()
```

---

If you want, I can also give:

✅ Java Swing version
✅ C# WinForms version
✅ Android version (Java/Kotlin)
Just tell me!
