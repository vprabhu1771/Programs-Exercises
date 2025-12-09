Sure! Let’s perform **Quick Sort** on the array:
**[7, 12, 9, 11, 3]**

There are different pivot selection strategies.
Here I’ll use **Last Element as Pivot** (common textbook method).

---

## 🔹 **Quick Sort – Step-by-Step Explanation (Each Pass)**

### **Initial Array**

```
[7, 12, 9, 11, 3]
```

Pivot = **last element = 3**

### **PASS 1**

Partition around pivot = 3
Compare every element with 3:

| Index | Element | Compare with Pivot (3) | Action  |
| ----- | ------- | ---------------------- | ------- |
| 0     | 7       | 7 > 3                  | No swap |
| 1     | 12      | 12 > 3                 | No swap |
| 2     | 9       | 9 > 3                  | No swap |
| 3     | 11      | 11 > 3                 | No swap |

👉 No element is smaller than 3.

Finally swap pivot with first element:

```
[3, 12, 9, 11, 7]
```

Pivot 3 is now at correct position (index 0)

🧩 Array is split into:

* Left side: **[]** (nothing)
* Right side: **[12, 9, 11, 7]**

---

### **PASS 2** (Right part sorting)

Working on: `[12, 9, 11, 7]`
Pivot = **7**

| Index | Element | Compare with 7 | Action  |
| ----- | ------- | -------------- | ------- |
| 1     | 12      | >7             | No swap |
| 2     | 9       | >7             | No swap |
| 3     | 11      | >7             | No swap |

Swap pivot with first element of this sub-array:

```
[3, 7, 9, 11, 12]
```

Pivot 7 correct position = index 1

🧩 Split:

* Left: `[]`
* Right: `[9, 11, 12]`

---

### **PASS 3** (Right part again)

Working on: `[9, 11, 12]`
Pivot = **12**

| Element | Compare | Action           |
| ------- | ------- | ---------------- |
| 9       | <12     | swap with itself |
| 11      | <12     | swap with itself |

(Already sorted around pivot)

Array remains:

```
[3, 7, 9, 11, 12]
```

Pivot at correct position (index 4)

🧩 Split:

* Left: `[9, 11]`
* Right: `[]`

---

### **PASS 4**

Working on `[9, 11]`
Pivot = **11**

| Element | Compare | Action           |
| ------- | ------- | ---------------- |
| 9       | <11     | swap with itself |

Final swap places pivot correctly:

```
[3, 7, 9, 11, 12]
```

Pivot 11 at index 3

🧩 Split:

* Left: `[9]`
* Right: `[]`

Only one element left → sorted.

---

## 🎯 Final Sorted Array:

```
[3, 7, 9, 11, 12]
```

---

If you want, I can now provide:

✔ C program
✔ C++ program
✔ Java program
✔ Python program
✔ Tkinter GUI simulation version

Which one should I give first?
