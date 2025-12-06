Here is a **clear explanation of the logic using long-division style steps**, with the example input **37**.

---

# ✅ **What the Program Does**

It **reverses** the digits of a number.

Input: `37`
Output: `73`

---

# ✅ **Logic Explained Using Long-Division Steps**

You start with:

```
num = 37
sum = 0
```

The loop:

```
while(num != 0)
```

will repeat until all digits are processed.

---

# ⭐ **Iteration 1**

### Step 1: Take the last digit (num % 10)

```
r = 37 % 10 = 7
```

This is like long division:

```
  37 ÷ 10  
   3 remainder 7
```

So **last digit = 7**

### Step 2: Remove last digit (num / 10)

```
num = 37 / 10 = 3
```

(10 goes into 37 three times, remainder is removed)

### Step 3: Build the reversed number

```
sum = sum * 10 + r
sum = 0 * 10 + 7 = 7
```

So after first round:

```
num = 3
sum = 7
```

---

# ⭐ **Iteration 2**

### Step 1: Take last digit

```
r = 3 % 10 = 3
```

### Step 2: Remove last digit

```
num = 3 / 10 = 0
```

### Step 3: Build reversed number

```
sum = 7 * 10 + 3 = 70 + 3 = 73
```

Now:

```
num = 0
sum = 73
```

Loop stops.

---

# 🎉 **Final Output**

```
reversed number : 73
```

---

# ✅ **Summary Table**

| Step  | num | r = num % 10 | sum = sum*10 + r |
| ----- | --- | ------------ | ---------------- |
| Start | 37  | –            | 0                |
| 1     | 37  | 7            | 7                |
| 2     | 3   | 3            | 73               |

---

If you'd like, I can also draw the long-division diagram or generalize the explanation for any number.