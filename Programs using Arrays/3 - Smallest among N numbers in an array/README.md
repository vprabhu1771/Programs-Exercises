Here are clean, correct programs for **Smallest among N numbers in an array** in:

✔ **C**
✔ **C++**
✔ **Java**
✔ **Python**
✔ **Python Tkinter (GUI)**

---

# ✅ **C Program**

```c
#include <stdio.h>

int main() {
    int a[30], n, i, smallest;

    printf("\nEnter number of elements: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++)
        scanf("%d", &a[i]);

    smallest = a[0];

    for(i = 1; i < n; i++) {
        if(a[i] < smallest)
            smallest = a[i];
    }

    printf("\nSmallest Element: %d", smallest);

    return 0;
}
```

---

# ✅ **C++ Program**

```cpp
#include <iostream>
using namespace std;

int main() {
    int a[30], n, smallest;

    cout << "Enter number of elements: ";
    cin >> n;

    for(int i = 0; i < n; i++)
        cin >> a[i];

    smallest = a[0];

    for(int i = 1; i < n; i++)
        if(a[i] < smallest)
            smallest = a[i];

    cout << "Smallest Element: " << smallest;

    return 0;
}
```

---

# ✅ **Java Program**

```java
import java.util.Scanner;

public class SmallestInArray {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of elements: ");
        int n = sc.nextInt();

        int[] a = new int[n];

        for(int i = 0; i < n; i++)
            a[i] = sc.nextInt();

        int smallest = a[0];

        for(int i = 1; i < n; i++)
            if(a[i] < smallest)
                smallest = a[i];

        System.out.println("Smallest Element: " + smallest);
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

smallest = a[0]

for i in range(1, n):
    if a[i] < smallest:
        smallest = a[i]

print("Smallest Element:", smallest)
```

---

# ✅ **Python Tkinter GUI**

Enter numbers separated by spaces → program finds smallest.

```python
import tkinter as tk
from tkinter import messagebox

def find_smallest():
    try:
        nums = list(map(int, entry.get().split()))
        smallest = min(nums)
        result_label.config(text=f"Smallest Number: {smallest}")
    except:
        messagebox.showerror("Error", "Please enter valid integers separated by spaces")

root = tk.Tk()
root.title("Find Smallest Number")
root.geometry("350x200")

tk.Label(root, text="Enter numbers (space separated):").pack(pady=5)

entry = tk.Entry(root, width=30)
entry.pack(pady=5)

btn = tk.Button(root, text="Find Smallest", command=find_smallest)
btn.pack(pady=10)

result_label = tk.Label(root, text="Smallest Number: ")
result_label.pack(pady=10)

root.mainloop()
```

---

If you need:
➡ Algorithm
➡ Flowchart
➡ Program using functions
➡ Program using dynamic memory

Just tell me!
