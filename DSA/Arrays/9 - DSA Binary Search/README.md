## 🔍 DSA – Binary Search

**Languages:** C, C++, Java, Python, Tkinter
**Array:** `[10, 20, 30, 40, 50]`

---

### ⚠️ Important Note

Binary Search **works only on a sorted array**.

Your array:

```
[10, 20, 30, 40, 50]
```

✔ Already **sorted**, so Binary Search can be applied directly.

---

## 🧠 Binary Search – Concept

Binary Search repeatedly divides the search interval in half.

**Steps:**

1. Find the middle element
2. Compare key with middle
3. If equal → found
4. If smaller → search left half
5. If larger → search right half

**Time Complexity:** `O(log n)`
**Space Complexity:** `O(1)` (Iterative)

---

## 📊 Example Trace

Search key = **40**

| Step | Low | High | Mid | A[mid] | Action       |
| ---- | --- | ---- | --- | ------ | ------------ |
| 1    | 0   | 4    | 2   | 30     | Search Right |
| 2    | 3   | 4    | 3   | 40     | ✅ Found      |

---

## 💻 C Program

```c
#include <stdio.h>

int binarySearch(int arr[], int n, int key) {
    int low = 0, high = n - 1;

    while (low <= high) {
        int mid = (low + high) / 2;

        if (arr[mid] == key)
            return mid;
        else if (arr[mid] < key)
            low = mid + 1;
        else
            high = mid - 1;
    }
    return -1;
}

int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int key = 40;

    int result = binarySearch(arr, 5, key);

    if (result != -1)
        printf("Element found at index %d", result);
    else
        printf("Element not found");

    return 0;
}
```

---

## 💻 C++ Program

```cpp
#include <iostream>
using namespace std;

int binarySearch(int arr[], int n, int key) {
    int low = 0, high = n - 1;

    while (low <= high) {
        int mid = (low + high) / 2;

        if (arr[mid] == key)
            return mid;
        else if (arr[mid] < key)
            low = mid + 1;
        else
            high = mid - 1;
    }
    return -1;
}

int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int key = 40;

    int result = binarySearch(arr, 5, key);

    if (result != -1)
        cout << "Element found at index " << result;
    else
        cout << "Element not found";

    return 0;
}
```

---

## ☕ Java Program

```java
class BinarySearch {
    static int binarySearch(int arr[], int key) {
        int low = 0, high = arr.length - 1;

        while (low <= high) {
            int mid = (low + high) / 2;

            if (arr[mid] == key)
                return mid;
            else if (arr[mid] < key)
                low = mid + 1;
            else
                high = mid - 1;
        }
        return -1;
    }

    public static void main(String[] args) {
        int arr[] = {10, 20, 30, 40, 50};
        int key = 40;

        int result = binarySearch(arr, key);

        if (result != -1)
            System.out.println("Element found at index " + result);
        else
            System.out.println("Element not found");
    }
}
```

---

## 🐍 Python Program

```python
def binary_search(arr, key):
    low = 0
    high = len(arr) - 1

    while low <= high:
        mid = (low + high) // 2

        if arr[mid] == key:
            return mid
        elif arr[mid] < key:
            low = mid + 1
        else:
            high = mid - 1

    return -1


arr = [10, 20, 30, 40, 50]
key = 40

result = binary_search(arr, key)

if result != -1:
    print("Element found at index", result)
else:
    print("Element not found")
```

---

## 🖼️ Tkinter – Binary Search Simulation

```python
import tkinter as tk

def binary_search():
    arr = [10, 20, 30, 40, 50]
    key = int(entry.get())

    low, high = 0, len(arr) - 1
    steps = ""

    while low <= high:
        mid = (low + high) // 2
        steps += f"Low={low}, High={high}, Mid={mid}, Value={arr[mid]}\n"

        if arr[mid] == key:
            result.set(f"Found at index {mid}\n\n{steps}")
            return
        elif arr[mid] < key:
            low = mid + 1
        else:
            high = mid - 1

    result.set("Element not found\n\n" + steps)

root = tk.Tk()
root.title("Binary Search")

tk.Label(root, text="Enter element to search").pack()
entry = tk.Entry(root)
entry.pack()

tk.Button(root, text="Search", command=binary_search).pack()

result = tk.StringVar()
tk.Label(root, textvariable=result, justify="left").pack()

root.mainloop()
```

---

## ✅ Key Takeaways

✔ Binary Search needs **sorted data**
✔ Much faster than Linear Search
✔ Widely used in **DSA & interviews**

If you want:
✔ Recursive version
✔ Animated step-by-step UI
✔ Comparison with Linear Search

Just tell me 😊
