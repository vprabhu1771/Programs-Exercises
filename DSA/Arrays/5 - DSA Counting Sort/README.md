Below is a **complete Counting Sort explanation + implementations** in **C, C++, Java, Python**, and an **optional Tkinter visualization**, starting from your array:

```
Unsorted array = [2, 3, 0, 2, 3, 2]
```

---

## 🔹 What is Counting Sort?

Counting Sort is a **non-comparison sorting algorithm** used when:

* Elements are **non-negative integers**
* **Range (max value)** is not very large

**Time Complexity:**

* Best / Avg / Worst → **O(n + k)**

  * `n` = number of elements
  * `k` = max value

**Space Complexity:** **O(k)**

---

## 🔹 Step-by-Step Counting Sort (Table)

### Step 1: Find maximum value

```
Max = 3
```

### Step 2: Create count array (size = max + 1)

```
Index:   0 1 2 3
Count:   0 0 0 0
```

### Step 3: Count occurrences

```
Read 2 → count[2]++
Read 3 → count[3]++
Read 0 → count[0]++
Read 2 → count[2]++
Read 3 → count[3]++
Read 2 → count[2]++
```

```
Count array = [1, 0, 3, 2]
```

### Step 4: Rebuild sorted array

```
0 → 1 time
2 → 3 times
3 → 2 times
```

### ✅ Final Sorted Array

```
[0, 2, 2, 2, 3, 3]
```

---

## 🔹 C Implementation

```c
#include <stdio.h>

int main() {
    int arr[] = {2, 3, 0, 2, 3, 2};
    int n = 6, max = 3;
    int count[4] = {0};

    for (int i = 0; i < n; i++)
        count[arr[i]]++;

    int index = 0;
    for (int i = 0; i <= max; i++) {
        while (count[i]--)
            arr[index++] = i;
    }

    printf("Sorted Array: ");
    for (int i = 0; i < n; i++)
        printf("%d ", arr[i]);

    return 0;
}
```

---

## 🔹 C++ Implementation

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {2, 3, 0, 2, 3, 2};
    int n = 6, max = 3;
    int count[4] = {0};

    for (int i = 0; i < n; i++)
        count[arr[i]]++;

    int index = 0;
    for (int i = 0; i <= max; i++) {
        while (count[i]--)
            arr[index++] = i;
    }

    cout << "Sorted Array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";

    return 0;
}
```

---

## 🔹 Java Implementation

```java
public class CountingSort {
    public static void main(String[] args) {
        int[] arr = {2, 3, 0, 2, 3, 2};
        int max = 3;
        int[] count = new int[max + 1];

        for (int num : arr)
            count[num]++;

        int index = 0;
        for (int i = 0; i <= max; i++) {
            while (count[i]-- > 0)
                arr[index++] = i;
        }

        System.out.print("Sorted Array: ");
        for (int num : arr)
            System.out.print(num + " ");
    }
}
```

---

## 🔹 Python Implementation

```python
arr = [2, 3, 0, 2, 3, 2]
max_val = max(arr)
count = [0] * (max_val + 1)

for num in arr:
    count[num] += 1

sorted_arr = []
for i in range(len(count)):
    sorted_arr.extend([i] * count[i])

print("Sorted Array:", sorted_arr)
```

---

## 🔹 Tkinter Visualization (Animated)

```python
import tkinter as tk
import time

arr = [2, 3, 0, 2, 3, 2]
count = [0] * (max(arr) + 1)

root = tk.Tk()
root.title("Counting Sort Visualization")

label = tk.Label(root, font=("Arial", 16))
label.pack()

for num in arr:
    count[num] += 1
    label.config(text=f"Counting: {count}")
    root.update()
    time.sleep(1)

sorted_arr = []
for i in range(len(count)):
    for _ in range(count[i]):
        sorted_arr.append(i)
        label.config(text=f"Sorted: {sorted_arr}")
        root.update()
        time.sleep(1)

root.mainloop()
```

---

## 🔹 When to Use Counting Sort?

✔ Small integer range
✔ No comparisons needed
✔ Very fast for frequency-based problems

❌ Not suitable for large ranges
❌ Extra memory needed

---

If you want:
✅ **Stable Counting Sort**
✅ **Negative numbers support**
✅ **Bar-chart Tkinter animation**
✅ **Exam-ready notes PDF**

Just tell me 👌
