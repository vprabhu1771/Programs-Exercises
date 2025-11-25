Below are clean and correct programs for **Reverse the array elements** in:

✔ **C**
✔ **C++**
✔ **Java**
✔ **Python**
✔ **Python Tkinter GUI**

(Your original logic is preserved but cleaned.)

---

# ✅ **C Program – Reverse Array**

```c
#include <stdio.h>

int main() {
    int a[30], i, j, n, temp;

    printf("\nEnter number of elements: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++)
        scanf("%d", &a[i]);

    j = n - 1;  // last index
    i = 0;      // first index

    while(i < j) {
        temp = a[i];
        a[i] = a[j];
        a[j] = temp;
        i++;
        j--;
    }

    for(i = 0; i < n; i++)
        printf("%d\n", a[i]);

    return 0;
}
```

---

# ✅ **C++ Program – Reverse Array**

```cpp
#include <iostream>
using namespace std;

int main() {
    int a[30], n, i, j, temp;

    cout << "Enter number of elements: ";
    cin >> n;

    for(i = 0; i < n; i++)
        cin >> a[i];

    i = 0;
    j = n - 1;

    while(i < j) {
        temp = a[i];
        a[i] = a[j];
        a[j] = temp;
        i++;
        j--;
    }

    for(i = 0; i < n; i++)
        cout << a[i] << endl;

    return 0;
}
```

---

# ✅ **Java Program – Reverse Array**

```java
import java.util.Scanner;

public class ReverseArray {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n;
        int[] a = new int[30];

        System.out.print("Enter number of elements: ");
        n = sc.nextInt();

        for(int i = 0; i < n; i++)
            a[i] = sc.nextInt();

        int i = 0, j = n - 1, temp;

        while(i < j) {
            temp = a[i];
            a[i] = a[j];
            a[j] = temp;
            i++;
            j--;
        }

        for(i = 0; i < n; i++)
            System.out.println(a[i]);
    }
}
```

---

# ✅ **Python Program – Reverse Array**

(Same logic using list.)

```python
n = int(input("Enter number of elements: "))
a = []

for _ in range(n):
    a.append(int(input()))

i = 0
j = n - 1

while i < j:
    a[i], a[j] = a[j], a[i]
    i += 1
    j -= 1

for num in a:
    print(num)
```

---

# ✅ **Python Tkinter GUI – Reverse Array**

Input numbers → click → reversed output.

```python
import tkinter as tk
from tkinter import messagebox

def reverse_array():
    try:
        nums = list(map(int, entry.get().split()))
        i = 0
        j = len(nums) - 1

        while i < j:
            nums[i], nums[j] = nums[j], nums[i]
            i += 1
            j -= 1

        result_label.config(text="Reversed:\n" + " ".join(map(str, nums)))

    except:
        messagebox.showerror("Error", "Enter valid integers separated by spaces")

root = tk.Tk()
root.title("Reverse Array")
root.geometry("350x250")

tk.Label(root, text="Enter numbers (space separated):").pack(pady=5)

entry = tk.Entry(root, width=30)
entry.pack(pady=5)

tk.Button(root, text="Reverse", command=reverse_array).pack(pady=10)

result_label = tk.Label(root, text="", justify="left")
result_label.pack(pady=5)

root.mainloop()
```

---

If you want, I can also provide:
➡ Reverse array using **for loop**
➡ Reverse array using **recursion**
➡ Reverse array without using extra variable (using XOR swap)

Just tell me!
