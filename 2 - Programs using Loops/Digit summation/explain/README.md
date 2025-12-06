Sure! Let’s explain the logic step-by-step using **long division** for input **1234**.

---

### 🔹 What the code does?

It finds the **sum of all digits** of a number.

The idea:

1. Take last digit using `% 10`
2. Add it to `sum`
3. Remove last digit using integer division `/ 10`
4. Repeat until number becomes `0`

---

### 🔸 Input

```
n = 1234
sum = 0
```

---

## 🔹 Iteration-by-Iteration Breakdown

### ➤ **1st Iteration**

```
n = 1234
Last digit = n % 10 → 1234 % 10 = 4
sum = sum + 4 → 0 + 4 = 4
n = n / 10 → 1234 / 10 = 123
```

🧮 Status:

```
sum = 4
n = 123
```

---

### ➤ **2nd Iteration**

```
n = 123
Last digit = 123 % 10 = 3
sum = 4 + 3 = 7
n = 123 / 10 = 12
```

🧮 Status:

```
sum = 7
n = 12
```

---

### ➤ **3rd Iteration**

```
n = 12
Last digit = 12 % 10 = 2
sum = 7 + 2 = 9
n = 12 / 10 = 1
```

🧮 Status:

```
sum = 9
n = 1
```

---

### ➤ **4th Iteration**

```
n = 1
Last digit = 1 % 10 = 1
sum = 9 + 1 = 10
n = 1 / 10 = 0  → loop stops
```

🧮 Final:

```
sum = 10
n = 0
```

---

## 🔚 Output

```
The sum of digits is 10
```

---

If you want, I can also create a trace table for neatly showing each step.
