Here’s the logic explained **step-by-step using long division** idea:

---

### 🔹 Goal

Check whether the given number (example: **121**) is a **palindrome** — meaning the number reads the same forward and backward.

---

### 🔹 Concept of Long Division

Long division means we break a number digit-by-digit from the **right side** using:

```
remainder = num % 10   → gives last digit
num = num / 10         → removes last digit
```

Example: `121`

| Operation       | Result             |
| --------------- | ------------------ |
| `121 % 10` → 1  | Extract last digit |
| `121 / 10` → 12 | Remove last digit  |

---

### 🔹 How the Loop Works?

We start with:

```
sum = 0
temp = original number
```

Then in each loop step:

1️⃣ Take the **last digit** of the number
`r = num % 10`

2️⃣ Remove that digit from number
`num = num / 10`

3️⃣ Build the **reverse number**
`sum = sum * 10 + r`

---

### 🔹 Example (num = 121)

| Step  | num | r = num % 10 | sum before | sum after       | Explanation         |
| ----- | --- | ------------ | ---------- | --------------- | ------------------- |
| Start | 121 | -            | 0          | 0               | Initial values      |
| 1     | 121 | 1            | 0          | 0*10 + 1 = 1    | Reverse starts as 1 |
| 2     | 12  | 2            | 1          | 1*10 + 2 = 12   | Add next digit      |
| 3     | 1   | 1            | 12         | 12*10 + 1 = 121 | Reverse completed   |

Finally:

```
temp = 121
sum  = 121
```

✔ Both are equal → **Palindrome**

---

### 🔹 Why it works?

Because:

* `% 10` takes digits **one by one from the end**
* `sum * 10` **shifts digits to left**, just like writing in reverse order
* Adding `r` builds the reversed number

---

### 🔹 Final Check

```
if (temp == sum)
    → palindrome
else
    → not palindrome
```

---

### ⭐ Summary

This program:

* Extracts digits using **division and modulo**
* **Reverses** the number digit-by-digit
* Compares reversed number with original

---

If you'd like, I can provide a **diagram** or more examples (like 12321, 101, 123).
