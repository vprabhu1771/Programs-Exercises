# C

```c
#include<stdio.h>

int main()
{
    char data;
    
    printf("Enter an alphabet");
    
    scanf("%c", &data);
    
    if(data == 'a' || 
       data == 'A' || 
       data == 'e' || 
       data == 'E' || 
       data == 'i' || 
       data == 'I' ||
       data == 'o' ||
       data == 'O' ||
       data == 'u' ||
       data == 'U')
   {
       printf("%c is a vowel", data);
   }
   else
   {
       printf("%c is a consonant", data);
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
    char data;
    
    cout << "Enter an alphabet" <<endl;
    
    cin >> data;
    
    if(data == 'a' || 
       data == 'A' || 
       data == 'e' || 
       data == 'E' || 
       data == 'i' || 
       data == 'I' ||
       data == 'o' ||
       data == 'O' ||
       data == 'u' ||
       data == 'U')
   {       
        cout << data << " is a vowel" << endl;
   }
   else
   {       
        cout << data << " is a consonant" << endl;
   }
    
    return 0;
}
```

Here are the same **“vowel or consonant check”** programs written in **Java**, **Python**, and **Tkinter GUI**.

---

# ✅ **Java Version**

```java
import java.util.Scanner;

public class VowelCheck {
    public static void main(String[] args) {

        char data;

        Scanner sc = new Scanner(System.in);

        System.out.println("Enter an alphabet:");
        data = sc.next().charAt(0);

        if (data == 'a' || data == 'A' ||
            data == 'e' || data == 'E' ||
            data == 'i' || data == 'I' ||
            data == 'o' || data == 'O' ||
            data == 'u' || data == 'U') {

            System.out.println(data + " is a vowel");
        } else {
            System.out.println(data + " is a consonant");
        }
    }
}
```

---

# ✅ **Python Version**

```python
data = input("Enter an alphabet: ")

if data in 'aeiouAEIOU':
    print(f"{data} is a vowel")
else:
    print(f"{data} is a consonant")
```

---

# ✅ **Tkinter GUI Version (Python)**

A small GUI app that checks whether a character is vowel or consonant.

```python
import tkinter as tk
from tkinter import messagebox

def check_alpha():
    data = entry.get()

    if len(data) != 1 or not data.isalpha():
        messagebox.showerror("Error", "Please enter a single alphabet")
        return

    if data in 'aeiouAEIOU':
        messagebox.showinfo("Result", f"{data} is a vowel")
    else:
        messagebox.showinfo("Result", f"{data} is a consonant")

root = tk.Tk()
root.title("Vowel or Consonant Checker")

tk.Label(root, text="Enter an alphabet:").grid(row=0, column=0, padx=10, pady=10)

entry = tk.Entry(root)
entry.grid(row=0, column=1, padx=10)

btn = tk.Button(root, text="Check", command=check_alpha)
btn.grid(row=1, column=0, columnspan=2, pady=10)

root.mainloop()
```

---

If you want, I can also give:

✅ Java Swing version
✅ C# WinForms GUI
✅ Flutter UI
Just ask!

