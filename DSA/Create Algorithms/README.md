# Create Algorithms

Here are the **C, C++, and Java** versions of your Python program:

---

# ✅ **C Program**

```c
#include <stdio.h>

int main() {
    int my_array[] = {7, 12, 9, 4, 11, 8};
    int size = sizeof(my_array) / sizeof(my_array[0]);
    int minVal = my_array[0];

    for (int i = 1; i < size; i++) {
        if (my_array[i] < minVal) {
            minVal = my_array[i];
        }
    }

    printf("Lowest value: %d\n", minVal);

    return 0;
}
```
# Output
```
Lowest value: 4
```

---

# ✅ **C++ Program**

```cpp
#include <iostream>
using namespace std;

int main() {
    int my_array[] = {7, 12, 9, 4, 11, 8};
    int size = sizeof(my_array) / sizeof(my_array[0]);
    int minVal = my_array[0];

    for (int i = 1; i < size; i++) {
        if (my_array[i] < minVal) {
            minVal = my_array[i];
        }
    }

    cout << "Lowest value: " << minVal << endl;

    return 0;
}
```

# Output
```
Lowest value: 4
```

---

# ✅ **Java Program**

```java
public class Main {
    public static void main(String[] args) {
        int[] my_array = {7, 12, 9, 4, 11, 8};
        int minVal = my_array[0];

        for (int i = 1; i < my_array.length; i++) {
            if (my_array[i] < minVal) {
                minVal = my_array[i];
            }
        }

        System.out.println("Lowest value: " + minVal);
    }
}
```

# Output
```
Lowest value: 4
```

---

Here you go — **Python improved version + Tkinter GUI version** as you asked.

---

# ✅ **Improved Python Program**

```python
my_array = [7, 12, 9, 4, 11, 8]
minVal = my_array[0]

for i in my_array:
    if i < minVal:
        minVal = i

print("Lowest value:", minVal)
```

# Output
```
Lowest value: 4
```

---

# ✅ **Python Tkinter GUI Version**

This program displays the lowest value in a Tkinter window.

```python
import tkinter as tk

def find_min():
    my_array = [7, 12, 9, 4, 11, 8]
    minVal = my_array[0]

    for i in my_array:
        if i < minVal:
            minVal = i

    result_label.config(text=f"Lowest value: {minVal}")

# Tkinter window
root = tk.Tk()
root.title("Find Minimum Value")
root.geometry("300x200")

title_label = tk.Label(root, text="Find Lowest Value", font=("Arial", 14))
title_label.pack(pady=10)

btn = tk.Button(root, text="Show Lowest Value", command=find_min, font=("Arial", 12))
btn.pack(pady=10)

result_label = tk.Label(root, text="", font=("Arial", 12))
result_label.pack(pady=10)

root.mainloop()
```

---

If you want, I can also add:
✅ Textbox to enter your own array
✅ Display highest value
✅ Show sorted values
Just tell me!


Here is the **flowchart** for finding the minimum value in an array.

---

# ✅ **Flowchart: Find Minimum Value in an Array**

```
          ┌──────────────────────┐
          │      Start           │
          └──────────┬───────────┘
                     │
                     ▼
     ┌────────────────────────────────┐
     │ Initialize array: [7,12,9,4,11,8] │
     └─────────────────┬───────────────┘
                       │
                       ▼
        ┌─────────────────────────┐
        │ minVal = first element  │
        │        (7)              │
        └───────────┬────────────┘
                    │
                    ▼
        ┌─────────────────────────┐
        │ Loop through each value │
        └───────────┬────────────┘
                    │
             ┌──────▼──────┐
             │ Is i < min? │
             └──────┬──────┘
                    │Yes
                    ▼
        ┌─────────────────────────┐
        │   Update minVal = i     │
        └───────────┬────────────┘
                    │
                    │No
                    ▼
         ┌────────────────────────┐
         │   More items in list?  │
         └───────────┬────────────┘
                     │Yes
                     ▼
                  (Repeat)
                     │
                     ▼ No
        ┌─────────────────────────┐
        │ Print Lowest value (4) │
        └───────────┬────────────┘
                    │
                    ▼
          ┌──────────────────────┐
          │         End          │
          └──────────────────────┘
```

---

If you want, I can also generate this flowchart as an **image**.
