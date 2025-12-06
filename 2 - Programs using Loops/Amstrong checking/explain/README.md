Sure! Let’s explain the **Armstrong number** logic step-by-step using **long division** for input **153**.

---

### 🔹 What is happening in the code?

It checks whether a number is an **Armstrong number**
(for 3-digit numbers → sum of cubes of digits = original number)

Formula example:
153 → (1^3 + 5^3 + 3^3 = 153)

---

### 🔸 Input

```
Enter a number: 153
```

Initial values:

```
ams = 153   (stored copy of original number)
num = 153
sum = 0
```

---

## 🔹 Long Division Breakdown (Digit by Digit)

### ➤ **1st Iteration**

```
num = 153
r = num % 10 → 153 % 10 = 3 (last digit)
sum = sum + (r * r * r)
    = 0 + (3 * 3 * 3)
    = 27
num = num / 10 → 153 / 10 = 15 (integer division)
```

🧮 Status:

```
sum = 27
num = 15
```

---

### ➤ **2nd Iteration**

```
num = 15
r = 15 % 10 = 5
sum = 27 + (5 * 5 * 5)
    = 27 + 125
    = 152
num = 15 / 10 = 1
```

🧮 Status:

```
sum = 152
num = 1
```

---

### ➤ **3rd Iteration**

```
num = 1
r = 1 % 10 = 1
sum = 152 + (1 * 1 * 1)
    = 152 + 1
    = 153
num = 1 / 10 = 0  (loop stops)
```

🧮 Final:

```
sum = 153
num = 0
```

---

## 🔚 Final Check

```
ams (original) = 153
sum (cube total) = 153
```

✔ They are equal → **153 is an Armstrong number**

---

### 📝 Output

```
153 is an Armstrong number
```

---

If you want, I can provide a trace table format for classroom notes too.
