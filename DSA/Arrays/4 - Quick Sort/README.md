Perfect! Here are **all the implementations of Quick Sort** using the same example
`[7, 12, 9, 11, 3]` ✔ C ✔ C++ ✔ Java ✔ Python ✔ Tkinter GUI

---

# ✅ **1️⃣ Quick Sort – C Program**

```c
#include <stdio.h>

void swap(int *a, int *b) {
    int t = *a;
    *a = *b;
    *b = t;
}

int partition(int arr[], int low, int high) {
    int pivot = arr[high];
    int i = (low - 1);

    for (int j = low; j < high; j++) {
        if (arr[j] < pivot) {
            i++;
            swap(&arr[i], &arr[j]);
        }
    }
    swap(&arr[i + 1], &arr[high]);
    return (i + 1);
}

void quickSort(int arr[], int low, int high) {
    if (low < high) {
        int pi = partition(arr, low, high);
        quickSort(arr, low, pi - 1);
        quickSort(arr, pi + 1, high);
    }
}

int main() {
    int arr[] = {7, 12, 9, 11, 3};
    int n = sizeof(arr) / sizeof(arr[0]);

    quickSort(arr, 0, n - 1);

    printf("Sorted array: ");
    for (int i = 0; i < n; i++)
        printf("%d ", arr[i]);

    return 0;
}
```

---

# ✅ **2️⃣ Quick Sort – C++ Program**

```cpp
#include <iostream>
using namespace std;

void swap(int &a, int &b) {
    int t = a;
    a = b;
    b = t;
}

int partition(int arr[], int low, int high) {
    int pivot = arr[high];
    int i = (low - 1);

    for (int j = low; j < high; j++) {
        if (arr[j] < pivot) {
            i++;
            swap(arr[i], arr[j]);
        }
    }
    swap(arr[i + 1], arr[high]);
    return i + 1;
}

void quickSort(int arr[], int low, int high) {
    if (low < high) {
        int pi = partition(arr, low, high);
        quickSort(arr, low, pi - 1);
        quickSort(arr, pi + 1, high);
    }
}

int main() {
    int arr[] = {7, 12, 9, 11, 3};
    int n = sizeof(arr) / sizeof(arr[0]);

    quickSort(arr, 0, n - 1);

    cout << "Sorted array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";

    return 0;
}
```

---

# ✅ **3️⃣ Quick Sort – Java Program**

```java
class QuickSort {

    static void swap(int[] arr, int i, int j) {
        int t = arr[i];
        arr[i] = arr[j];
        arr[j] = t;
    }

    static int partition(int[] arr, int low, int high) {
        int pivot = arr[high];
        int i = low - 1;

        for (int j = low; j < high; j++) {
            if (arr[j] < pivot) {
                i++;
                swap(arr, i, j);
            }
        }
        swap(arr, i + 1, high);
        return i + 1;
    }

    static void quickSort(int[] arr, int low, int high) {
        if (low < high) {
            int pi = partition(arr, low, high);
            quickSort(arr, low, pi - 1);
            quickSort(arr, pi + 1, high);
        }
    }

    public static void main(String[] args) {
        int[] arr = {7, 12, 9, 11, 3};
        quickSort(arr, 0, arr.length - 1);

        System.out.print("Sorted array: ");
        for (int num : arr)
            System.out.print(num + " ");
    }
}
```

---

# ✅ **4️⃣ Quick Sort – Python Program**

```python
def partition(arr, low, high):
    pivot = arr[high]
    i = low - 1

    for j in range(low, high):
        if arr[j] < pivot:
            i += 1
            arr[i], arr[j] = arr[j], arr[i]

    arr[i + 1], arr[high] = arr[high], arr[i + 1]
    return i + 1

def quickSort(arr, low, high):
    if low < high:
        pi = partition(arr, low, high)
        quickSort(arr, low, pi - 1)
        quickSort(arr, pi + 1, high)

arr = [7, 12, 9, 11, 3]
quickSort(arr, 0, len(arr) - 1)
print("Sorted array:", arr)
```

---

# 🎨 **5️⃣ Quick Sort Simulation – Tkinter GUI**

This GUI visualizes each partitioning step.

> You can paste into a Python file and run.

```python
import tkinter as tk
import time

arr = [7, 12, 9, 11, 3]

root = tk.Tk()
root.title("Quick Sort Visualization")

canvas = tk.Canvas(root, width=400, height=200)
canvas.pack()

def draw(arr, color="blue"):
    canvas.delete("all")
    x = 20
    for i, num in enumerate(arr):
        canvas.create_rectangle(x, 150-num*5, x+40, 150, fill=color)
        canvas.create_text(x+20, 160, text=str(num))
        x += 60
    root.update()
    time.sleep(1)

def partition(arr, low, high):
    pivot = arr[high]
    draw(arr, "yellow")
    i = low - 1
    for j in range(low, high):
        if arr[j] < pivot:
            i += 1
            arr[i], arr[j] = arr[j], arr[i]
            draw(arr, "green")
    arr[i + 1], arr[high] = arr[high], arr[i + 1]
    draw(arr, "red")
    return i + 1

def quickSort(arr, low, high):
    if low < high:
        pi = partition(arr, low, high)
        quickSort(arr, low, pi - 1)
        quickSort(arr, pi + 1, high)

draw(arr, "blue")
root.after(1000, lambda: quickSort(arr, 0, len(arr) - 1))
root.mainloop()
```

---

### 🎯 RESULT

All programs will output:

```
Sorted array: 3 7 9 11 12
```

---

If you want, I can also provide:
📌 Quick Sort with user input
📌 Step-by-step print inside each program
📌 Comments for exam/DSA notes
📌 GUI with sound / speed control

Would you like the **Merge Sort** next?
