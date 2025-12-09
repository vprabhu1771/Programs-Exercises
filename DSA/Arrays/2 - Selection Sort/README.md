Here is **Selection Sort** in all the languages you asked: **C, C++, Java, Python**, plus a **Tkinter GUI** version.

We will sort this starting array:

```
[7, 12, 9, 11, 3]
```

---

## 🔹 Selection Sort — Quick Explanation

* We divide the array into a **sorted** part (on the left) and **unsorted** part (on the right).
* On each pass:

  1. Find the **minimum** value in the unsorted part.
  2. Swap it with the **first element** of the unsorted part.
* Continue until the full array is sorted.

Final output:

```
[3, 7, 9, 11, 12]
```

---

## ✅ C Program – Selection Sort

```c
#include <stdio.h>

void selectionSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        int minIndex = i;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[minIndex]) {
                minIndex = j;
            }
        }
        int temp = arr[i];
        arr[i] = arr[minIndex];
        arr[minIndex] = temp;
    }
}

int main() {
    int arr[] = {7, 12, 9, 11, 3};
    int n = sizeof(arr) / sizeof(arr[0]);

    selectionSort(arr, n);

    printf("Sorted Array: ");
    for (int i = 0; i < n; i++)
        printf("%d ", arr[i]);
}
```

---

## ✅ C++ Program – Selection Sort

```cpp
#include <iostream>
using namespace std;

void selectionSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        int minIndex = i;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[minIndex]) {
                minIndex = j;
            }
        }
        swap(arr[i], arr[minIndex]);
    }
}

int main() {
    int arr[] = {7, 12, 9, 11, 3};
    int n = sizeof(arr) / sizeof(arr[0]);

    selectionSort(arr, n);

    cout << "Sorted Array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
}
```

---

## ☕ Java Program – Selection Sort

```java
public class SelectionSort {
    public static void main(String[] args) {
        int arr[] = {7, 12, 9, 11, 3};

        for (int i = 0; i < arr.length - 1; i++) {
            int minIndex = i;
            for (int j = i + 1; j < arr.length; j++) {
                if (arr[j] < arr[minIndex]) {
                    minIndex = j;
                }
            }
            int temp = arr[i];
            arr[i] = arr[minIndex];
            arr[minIndex] = temp;
        }

        System.out.print("Sorted Array: ");
        for (int num : arr)
            System.out.print(num + " ");
    }
}
```

---

## 🐍 Python Program – Selection Sort

```python
arr = [7, 12, 9, 11, 3]

for i in range(len(arr) - 1):
    min_index = i
    for j in range(i + 1, len(arr)):
        if arr[j] < arr[min_index]:
            min_index = j
    arr[i], arr[min_index] = arr[min_index], arr[i]

print("Sorted Array:", arr)
```

---

## 🎨 Tkinter Visualization — Selection Sort Animation

This GUI highlights updates by re-drawing after each swap.

```python
import tkinter as tk
import time

arr = [7, 12, 9, 11, 3]

def display_array():
    canvas.delete("all")
    x = 40
    for num in arr:
        canvas.create_text(x, 60, text=str(num), font=("Arial", 18))
        x += 50

def selection_sort():
    n = len(arr)
    for i in range(n - 1):
        min_index = i
        for j in range(i + 1, n):
            if arr[j] < arr[min_index]:
                min_index = j

        arr[i], arr[min_index] = arr[min_index], arr[i]
        display_array()
        root.update()
        time.sleep(0.8)

root = tk.Tk()
root.title("Selection Sort Visualization")

canvas = tk.Canvas(root, width=300, height=150)
canvas.pack()

display_array()

btn = tk.Button(root, text="Start Selection Sort", command=selection_sort)
btn.pack()

root.mainloop()
```

---

### If you want 👉

✔ Step-by-step explanation of each pass
✔ Colored animation (highlight smallest element)
✔ Swap count + pass count
✔ Graph bars instead of text (like real visualizers)

Would you like me to produce a **Step-By-Step explanation for Selection Sort** just like Bubble Sort earlier?
