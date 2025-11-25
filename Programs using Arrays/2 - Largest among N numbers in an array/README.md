Below are clean, correct implementations of **“Largest among N numbers in an array”** in:

✔ **C**
✔ **C++**
✔ **Java**
✔ **Python (basic)**
✔ **Python Tkinter GUI**

---

# ✅ **C Program**

```c
#include <stdio.h>

int main() {
    int a[30], n, i, largest;

    printf("\nEnter number of elements: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++) {
        scanf("%d", &a[i]);
    }

    largest = a[0];
    for(i = 1; i < n; i++) {
        if(a[i] > largest)
            largest = a[i];
    }

    printf("\nLargest Element: %d", largest);

    return 0;
}
```

---

# ✅ **C++ Program**

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, largest;
    int a[30];

    cout << "Enter number of elements: ";
    cin >> n;

    for(int i = 0; i < n; i++)
        cin >> a[i];

    largest = a[0];

    for(int i = 1; i < n; i++)
        if(a[i] > largest)
            largest = a[i];

    cout << "Largest Element: " << largest;
}
```

---

# ✅ **Java Program**

```java
import java.util.Scanner;

public class LargestInArray {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of elements: ");
        int n = sc.nextInt();

        int[] a = new int[n];

        for(int i = 0; i < n; i++)
            a[i] = sc.nextInt();

        int largest = a[0];

        for(int i = 1; i < n; i++)
            if(a[i] > largest)
                largest = a[i];

        System.out.println("Largest Element: " + largest);
    }
}
```

---

# ✅ **Python Program**

```python
n = int(input("Enter number of elements: "))
a = []

for _ in range(n):
    a.append(int(input()))

largest = a[0]

for i in range(1, n):
    if a[i] > largest:
        largest = a[i]

print("Largest Element:", largest)
```

---

# ✅ **Python Tkinter Program (GUI)**

This GUI accepts numbers separated by spaces and shows the largest number.

```python
import tkinter as tk
from tkinter import messagebox

def find_largest():
    try:
        nums = list(map(int, entry.get().split()))
        largest = max(nums)
        result_label.config(text=f"Largest Number: {largest}")
    except:
        messagebox.showerror("Error", "Please enter valid integers separated by spaces")

root = tk.Tk()
root.title("Find Largest Number")
root.geometry("350x200")

tk.Label(root, text="Enter numbers (space separated):").pack(pady=5)

entry = tk.Entry(root, width=30)
entry.pack(pady=5)

btn = tk.Button(root, text="Find Largest", command=find_largest)
btn.pack(pady=10)

result_label = tk.Label(root, text="Largest Number: ")
result_label.pack(pady=5)

root.mainloop()
```

---

If you want, I can also provide:
👉 **Flowchart**
👉 **Algorithm / Pseudocode**
👉 **C Program using functions**
👉 **Tkinter advanced UI with listbox**

Just tell me!
