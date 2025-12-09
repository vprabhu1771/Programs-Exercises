Here are **Insertion Sort implementations** in **C, C++, Java, Python**, plus a **Tkinter visualization**, all using your array:

```
[7, 12, 9, 11, 3]
```

After the code, I will give you the **full step-by-step pass explanation** (like Bubble & Selection Sort earlier).
➡️ Scroll down for that explanation.

---

# ✅ C Program – Insertion Sort

```c
#include <stdio.h>

void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;

        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
}

int main() {
    int arr[] = {7, 12, 9, 11, 3};
    int n = sizeof(arr) / sizeof(arr[0]);

    insertionSort(arr, n);

    printf("Sorted Array: ");
    for (int i = 0; i < n; i++)
        printf("%d ", arr[i]);
}
```

---

# ✅ C++ Program – Insertion Sort

```cpp
#include <iostream>
using namespace std;

void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;

        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
}

int main() {
    int arr[] = {7, 12, 9, 11, 3};
    int n = sizeof(arr) / sizeof(arr[0]);

    insertionSort(arr, n);

    cout << "Sorted Array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
}
```

---

# ☕ Java Program – Insertion Sort

```java
public class InsertionSort {
    public static void main(String[] args) {
        int arr[] = {7, 12, 9, 11, 3};

        for (int i = 1; i < arr.length; i++) {
            int key = arr[i];
            int j = i - 1;

            while (j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j];
                j--;
            }
            arr[j + 1] = key;
        }

        System.out.print("Sorted Array: ");
        for (int num : arr)
            System.out.print(num + " ");
    }
}
```

---

# 🐍 Python Program – Insertion Sort

```python
arr = [7, 12, 9, 11, 3]

for i in range(1, len(arr)):
    key = arr[i]
    j = i - 1

    while j >= 0 and arr[j] > key:
        arr[j + 1] = arr[j]
        j -= 1

    arr[j + 1] = key

print("Sorted Array:", arr)
```

---

# 🎨 Tkinter Visualization – Insertion Sort Animation

```python
import tkinter as tk
import time

arr = [7, 12, 9, 11, 3]

def show():
    canvas.delete("all")
    x = 40
    for num in arr:
        canvas.create_text(x, 60, text=str(num), font=("Arial", 18))
        x += 50

def insertion_sort():
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1

        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            show(); root.update(); time.sleep(0.7)
            j -= 1

        arr[j + 1] = key
        show(); root.update(); time.sleep(0.7)

root = tk.Tk()
root.title("Insertion Sort Visualizer")

canvas = tk.Canvas(root, width=350, height=150)
canvas.pack()

show()

tk.Button(root, text="Start Insertion Sort", command=insertion_sort).pack()

root.mainloop()
```

---

# 🧠 Step-by-Step Insertion Sort (With Explanation)

**Initial array:**
`[7, 12, 9, 11, 3]`

We insert each element into the sorted left side.

---

### ⭐ Pass 1: Insert `12` (i = 1)

Sorted part: `[7]`
Compare: `12 ≥ 7` → no shift
Place `12` properly → no change

Array: `[7, 12, 9, 11, 3]`

---

### ⭐ Pass 2: Insert `9` (i = 2)

Sorted part: `[7, 12]`

* Compare `9 < 12` → shift `12`
  → `[7, 12, 12, 11, 3]`
* Compare `9 ≥ 7` → stop

Insert `9` → `[7, 9, 12, 11, 3]`

---

### ⭐ Pass 3: Insert `11` (i = 3)

Sorted part: `[7, 9, 12]`

* Compare `11 < 12` → shift `12`
  → `[7, 9, 12, 12, 3]`
* Compare `11 ≥ 9` → stop

Insert `11` → `[7, 9, 11, 12, 3]`

---

### ⭐ Pass 4: Insert `3` (i = 4)

Sorted part: `[7, 9, 11, 12]`

* `3 < 12` → shift → `[7, 9, 11, 12, 12]`
* `3 < 11` → shift → `[7, 9, 11, 11, 12]`
* `3 < 9`  → shift → `[7, 9, 9, 11, 12]`
* `3 < 7`  → shift → `[7, 7, 9, 11, 12]`
* Now j = -1 → stop, insert at start

Insert `3`:
`[3, 7, 9, 11, 12]`

---

# 🎯 Final Sorted Array

`[3, 7, 9, 11, 12]`

---

## 📌 Summary Table

| Pass | Key | Shifts | Result              |
| ---: | --: | -----: | ------------------- |
|    1 |  12 |      0 | `[7, 12, 9, 11, 3]` |
|    2 |   9 |      1 | `[7, 9, 12, 11, 3]` |
|    3 |  11 |      1 | `[7, 9, 11, 12, 3]` |
|    4 |   3 |      4 | `[3, 7, 9, 11, 12]` |

🔹 Comparisons fewer than Bubble/Selection
🔹 Great for **nearly sorted** arrays

---

If you want, I can also provide:

✔ Trace output printed in each language
✔ Color-highlighted Tkinter animation (current key and shifts)
✔ Time complexity table + best/worst cases comparison

Would you like me to do **Merge Sort**, **Quick Sort**, or **Heap Sort** next in the same style?
