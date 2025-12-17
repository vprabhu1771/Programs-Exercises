Below is a **complete DSA Radix Sort explanation** with **step-by-step process**, followed by **C, C++, Java, Python implementations**, and a **Tkinter GUI demo**.

---

# 🔢 Radix Sort (LSD – Least Significant Digit)

### 📌 Input (Unsorted Array)

```
[33, 45, 40, 25, 17, 24]
```

Radix Sort works **digit by digit**, starting from the **least significant digit (units place)**.

---

## 🧠 Step-by-Step Explanation

### 🔹 Step 1: Find maximum number

```
Max = 45 → 2 digits
```

So we need **2 passes**:

1. Units place
2. Tens place

---

### 🔹 Step 2: Sort by Units Digit

| Number | Units Digit |
| ------ | ----------- |
| 33     | 3           |
| 45     | 5           |
| 40     | 0           |
| 25     | 5           |
| 17     | 7           |
| 24     | 4           |

**Buckets (0–9):**

```
0 → [40]
3 → [33]
4 → [24]
5 → [45, 25]
7 → [17]
```

**Array after pass 1**

```
[40, 33, 24, 45, 25, 17]
```

---

### 🔹 Step 3: Sort by Tens Digit

| Number | Tens Digit |
| ------ | ---------- |
| 40     | 4          |
| 33     | 3          |
| 24     | 2          |
| 45     | 4          |
| 25     | 2          |
| 17     | 1          |

**Buckets:**

```
1 → [17]
2 → [24, 25]
3 → [33]
4 → [40, 45]
```

**Final Sorted Array**

```
[17, 24, 25, 33, 40, 45]
```

---

## ✅ Time & Space Complexity

| Case                        | Complexity         |
| --------------------------- | ------------------ |
| Best / Avg / Worst          | **O(d × (n + k))** |
| Space                       | **O(n + k)**       |
| *d = digits, k = base (10)* |                    |

---

# 💻 Implementations

---

## 🟦 C Program

```c
#include <stdio.h>

int getMax(int arr[], int n) {
    int max = arr[0];
    for (int i = 1; i < n; i++)
        if (arr[i] > max) max = arr[i];
    return max;
}

void countingSort(int arr[], int n, int exp) {
    int output[n], count[10] = {0};

    for (int i = 0; i < n; i++)
        count[(arr[i] / exp) % 10]++;

    for (int i = 1; i < 10; i++)
        count[i] += count[i - 1];

    for (int i = n - 1; i >= 0; i--) {
        output[count[(arr[i] / exp) % 10] - 1] = arr[i];
        count[(arr[i] / exp) % 10]--;
    }

    for (int i = 0; i < n; i++)
        arr[i] = output[i];
}

void radixSort(int arr[], int n) {
    int max = getMax(arr, n);
    for (int exp = 1; max / exp > 0; exp *= 10)
        countingSort(arr, n, exp);
}

int main() {
    int arr[] = {33, 45, 40, 25, 17, 24};
    int n = 6;
    radixSort(arr, n);

    for (int i = 0; i < n; i++)
        printf("%d ", arr[i]);
}
```

---

## 🟦 C++ Program

```cpp
#include <iostream>
using namespace std;

int getMax(int arr[], int n) {
    int max = arr[0];
    for (int i = 1; i < n; i++)
        if (arr[i] > max) max = arr[i];
    return max;
}

void countingSort(int arr[], int n, int exp) {
    int output[n], count[10] = {0};

    for (int i = 0; i < n; i++)
        count[(arr[i] / exp) % 10]++;

    for (int i = 1; i < 10; i++)
        count[i] += count[i - 1];

    for (int i = n - 1; i >= 0; i--) {
        output[count[(arr[i] / exp) % 10] - 1] = arr[i];
        count[(arr[i] / exp) % 10]--;
    }

    for (int i = 0; i < n; i++)
        arr[i] = output[i];
}

void radixSort(int arr[], int n) {
    int max = getMax(arr, n);
    for (int exp = 1; max / exp > 0; exp *= 10)
        countingSort(arr, n, exp);
}

int main() {
    int arr[] = {33, 45, 40, 25, 17, 24};
    radixSort(arr, 6);
    for (int i : arr) cout << i << " ";
}
```

---

## 🟨 Java Program

```java
import java.util.Arrays;

class RadixSort {
    static void radixSort(int[] arr) {
        int max = Arrays.stream(arr).max().getAsInt();

        for (int exp = 1; max / exp > 0; exp *= 10)
            countingSort(arr, exp);
    }

    static void countingSort(int[] arr, int exp) {
        int n = arr.length;
        int[] output = new int[n];
        int[] count = new int[10];

        for (int i : arr)
            count[(i / exp) % 10]++;

        for (int i = 1; i < 10; i++)
            count[i] += count[i - 1];

        for (int i = n - 1; i >= 0; i--) {
            output[--count[(arr[i] / exp) % 10]] = arr[i];
        }

        System.arraycopy(output, 0, arr, 0, n);
    }

    public static void main(String[] args) {
        int[] arr = {33, 45, 40, 25, 17, 24};
        radixSort(arr);
        System.out.println(Arrays.toString(arr));
    }
}
```

---

## 🟩 Python Program

```python
def radix_sort(arr):
    max_num = max(arr)
    exp = 1

    while max_num // exp > 0:
        buckets = [[] for _ in range(10)]

        for num in arr:
            buckets[(num // exp) % 10].append(num)

        arr = [num for bucket in buckets for num in bucket]
        exp *= 10

    return arr

arr = [33, 45, 40, 25, 17, 24]
print(radix_sort(arr))
```

---

# 🖥️ Tkinter Visualization

```python
import tkinter as tk

def radix_sort_visual():
    arr = [33, 45, 40, 25, 17, 24]
    text.delete("1.0", tk.END)

    exp = 1
    max_num = max(arr)

    while max_num // exp > 0:
        buckets = [[] for _ in range(10)]

        for num in arr:
            buckets[(num // exp) % 10].append(num)

        arr = [num for bucket in buckets for num in bucket]
        text.insert(tk.END, f"After exp={exp}: {arr}\n")
        exp *= 10

root = tk.Tk()
root.title("Radix Sort Visualization")

btn = tk.Button(root, text="Start Radix Sort", command=radix_sort_visual)
btn.pack(pady=10)

text = tk.Text(root, height=10, width=40)
text.pack()

root.mainloop()
```

---

## 🎯 Final Output

```
[17, 24, 25, 33, 40, 45]
```

---

If you want:
✔ **Animated bars**
✔ **Step-by-step bucket view**
✔ **Comparison with Counting Sort**
✔ **Exam-ready notes PDF**

Just tell me 😊
