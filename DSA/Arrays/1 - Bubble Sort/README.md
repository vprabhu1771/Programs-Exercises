Below is **Bubble Sort** for your example array **[7, 12, 9, 11, 3]** in **C, C++, Java, Python**, and also a **Tkinter GUI** version (Python).

---

## 🔹 Algorithm – Bubble Sort (Explanation)

* We repeatedly compare each pair of adjacent items.
* If they are in the wrong order → swap them.
* Each full pass pushes the **largest** remaining element to the end.
* Continue until the array is fully sorted.

Input:

```
[7, 12, 9, 11, 3]
```

Output:

```
[3, 7, 9, 11, 12]
```

---

## ✅ C Program – Bubble Sort

```c
#include <stdio.h>

void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}

int main() {
    int arr[] = {7, 12, 9, 11, 3};
    int n = sizeof(arr) / sizeof(arr[0]);

    bubbleSort(arr, n);

    printf("Sorted Array: ");
    for (int i = 0; i < n; i++)
        printf("%d ", arr[i]);

    return 0;
}
```

---

## ✅ C++ Program – Bubble Sort

```cpp
#include <iostream>
using namespace std;

void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                swap(arr[j], arr[j + 1]);
            }
        }
    }
}

int main() {
    int arr[] = {7, 12, 9, 11, 3};
    int n = sizeof(arr) / sizeof(arr[0]);

    bubbleSort(arr, n);

    cout << "Sorted Array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
}
```

---

## ☕ Java Program – Bubble Sort

```java
public class BubbleSort {
    public static void main(String[] args) {
        int arr[] = {7, 12, 9, 11, 3};

        for (int i = 0; i < arr.length - 1; i++) {
            for (int j = 0; j < arr.length - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }

        System.out.print("Sorted Array: ");
        for (int num : arr)
            System.out.print(num + " ");
    }
}
```

---

## 🐍 Python Program – Bubble Sort

```python
arr = [7, 12, 9, 11, 3]

for i in range(len(arr) - 1):
    for j in range(len(arr) - i - 1):
        if arr[j] > arr[j + 1]:
            arr[j], arr[j + 1] = arr[j + 1], arr[j]

print("Sorted Array:", arr)
```

---

## 🎨 Bubble Sort Visualization using Tkinter

This GUI shows the array and updates after each swap.

```python
import tkinter as tk
import time

arr = [7, 12, 9, 11, 3]

def bubble_sort():
    n = len(arr)
    for i in range(n - 1):
        for j in range(n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
                display_array()
                root.update()
                time.sleep(0.7)

def display_array():
    canvas.delete("all")
    x = 50
    for num in arr:
        canvas.create_text(x, 50, text=str(num), font=("Arial", 18))
        x += 50

root = tk.Tk()
root.title("Bubble Sort Visualization")

canvas = tk.Canvas(root, width=300, height=150)
canvas.pack()

display_array()

btn = tk.Button(root, text="Start Bubble Sort", command=bubble_sort)
btn.pack()

root.mainloop()
```

---

### If you want 🔽

✔ Color animation for swaps
✔ Step-by-step buttons (Next Pass, Reset)
✔ Display pass number and swaps count
✔ Larger arrays and graph bars instead of text

Just tell me — I can upgrade the GUI for you!
