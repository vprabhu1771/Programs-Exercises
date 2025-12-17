Below is a **DSA – Linear Search** explanation with **step-by-step working** and implementations in
**C, C++, Java, Python**, plus a **Tkinter GUI simulation**.

---

## 🔍 Linear Search (Sequential Search)

**Array (unsorted):**
`[10, 20, 30, 40, 50]`
**Key to search:** `40`

---

## 🧠 Algorithm (Step-by-Step)

1. Start from index `0`
2. Compare each element with the key
3. If match found → return index
4. If end reached → element not found

---

## 📊 Step-by-Step Table

| Step | Index | Element | Compare with 40 | Result  |
| ---- | ----- | ------- | --------------- | ------- |
| 1    | 0     | 10      | 10 == 40        | ❌       |
| 2    | 1     | 20      | 20 == 40        | ❌       |
| 3    | 2     | 30      | 30 == 40        | ❌       |
| 4    | 3     | 40      | 40 == 40        | ✅ Found |

✔ **Element found at index 3**

---

## ⏱ Time & Space Complexity

* **Best Case:** O(1)
* **Worst Case:** O(n)
* **Space Complexity:** O(1)

---

# 💻 Program Implementations

---

## ✅ C Program

```c
#include <stdio.h>

int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int n = 5, key = 40;

    for(int i = 0; i < n; i++) {
        if(arr[i] == key) {
            printf("Element found at index %d\n", i);
            return 0;
        }
    }

    printf("Element not found\n");
    return 0;
}
```

---

## ✅ C++ Program

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int key = 40;

    for(int i = 0; i < 5; i++) {
        if(arr[i] == key) {
            cout << "Element found at index " << i;
            return 0;
        }
    }

    cout << "Element not found";
    return 0;
}
```

---

## ✅ Java Program

```java
public class LinearSearch {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40, 50};
        int key = 40;

        for(int i = 0; i < arr.length; i++) {
            if(arr[i] == key) {
                System.out.println("Element found at index " + i);
                return;
            }
        }
        System.out.println("Element not found");
    }
}
```

---

## ✅ Python Program

```python
arr = [10, 20, 30, 40, 50]
key = 40

for i in range(len(arr)):
    if arr[i] == key:
        print(f"Element found at index {i}")
        break
else:
    print("Element not found")
```

---

# 🖥 Tkinter GUI – Linear Search Simulation

```python
import tkinter as tk

arr = [10, 20, 30, 40, 50]

def linear_search():
    key = int(entry.get())
    output.delete(0, tk.END)

    for i, val in enumerate(arr):
        output.insert(tk.END, f"Checking index {i} → {val}")
        if val == key:
            output.insert(tk.END, f"✔ Found at index {i}")
            return
    output.insert(tk.END, "❌ Element not found")

root = tk.Tk()
root.title("Linear Search Visualization")

tk.Label(root, text="Array: [10, 20, 30, 40, 50]").pack()
entry = tk.Entry(root)
entry.pack()

tk.Button(root, text="Search", command=linear_search).pack()

output = tk.Listbox(root, width=40)
output.pack()

root.mainloop()
```

---

## 🎯 Key Takeaways

✔ Works on **unsorted arrays**
✔ Simple but **inefficient for large data**
✔ Useful for **small datasets**

---

If you want next:
👉 **Binary Search**
👉 **Animated Tkinter step highlight**
👉 **Comparison table (Linear vs Binary)**
