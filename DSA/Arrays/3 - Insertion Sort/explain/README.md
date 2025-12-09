Nice — here’s a clear, step-by-step insertion-sort trace for the array **[7, 12, 9, 11, 3]** showing every comparison, each shift (movement of an element to the right), and the array after each action.

**Initial array:** `[7, 12, 9, 11, 3]`

---

# Pass 1 (i = 1, key = 12)

* Start: sorted part `[7]`, key = `12`.
* Compare `arr[0] (7)` > `key (12)`? → `7 > 12` → **No** (no shift).
* Place `key` at `arr[1]` (no actual change).

**Array after Pass 1:** `[7, 12, 9, 11, 3]`
Comparisons this pass: 1, shifts: 0

---

# Pass 2 (i = 2, key = 9)

* Start: sorted part `[7, 12]`, key = `9`.

1. Compare `arr[1] (12)` > `9`? → **Yes** → shift `12` right:

   * Action: `arr[2] = arr[1]` → array becomes `[7, 12, 12, 11, 3]`.
   * j becomes `0`.
2. Compare `arr[0] (7)` > `9`? → `7 > 9` → **No** → stop.

* Insert `key` at `arr[1]`: `arr[1] = 9`.

**Array after Pass 2:** `[7, 9, 12, 11, 3]`
Comparisons this pass: 2, shifts: 1

---

# Pass 3 (i = 3, key = 11)

* Start: sorted part `[7, 9, 12]`, key = `11`.

1. Compare `arr[2] (12)` > `11`? → **Yes** → shift `12` right:

   * Action: `arr[3] = arr[2]` → array becomes `[7, 9, 12, 12, 3]`.
   * j becomes `1`.
2. Compare `arr[1] (9)` > `11`? → `9 > 11` → **No** → stop.

* Insert `key` at `arr[2]`: `arr[2] = 11`.

**Array after Pass 3:** `[7, 9, 11, 12, 3]`
Comparisons this pass: 2, shifts: 1

---

# Pass 4 (i = 4, key = 3)

* Start: sorted part `[7, 9, 11, 12]`, key = `3`.

1. Compare `arr[3] (12)` > `3`? → **Yes** → shift `12` right:

   * `arr[4] = 12` → `[7, 9, 11, 12, 12]`, j → 2
2. Compare `arr[2] (11)` > `3`? → **Yes** → shift `11` right:

   * `arr[3] = 11` → `[7, 9, 11, 11, 12]`, j → 1
3. Compare `arr[1] (9)` > `3`? → **Yes** → shift `9` right:

   * `arr[2] = 9` → `[7, 9, 9, 11, 12]`, j → 0
4. Compare `arr[0] (7)` > `3`? → **Yes** → shift `7` right:

   * `arr[1] = 7` → `[7, 7, 9, 11, 12]`, j → -1
5. Now `j = -1` → stop the while loop and insert `key` at `arr[0]`:

   * `arr[0] = 3` → `[3, 7, 9, 11, 12]`.

**Array after Pass 4:** `[3, 7, 9, 11, 12]`
Comparisons this pass: 4, shifts: 4

---

# Final result & totals

* **Sorted array:** `[3, 7, 9, 11, 12]`
* **Total comparisons:** `1 + 2 + 2 + 4 = 9`
* **Total shifts (element moves to the right):** `0 + 1 + 1 + 4 = 6`

---

If you want, I can:

* Produce the **same printed trace** from code (Python or any other language) that logs every comparison and shift, or
* Give a **Tkinter animation** that highlights the `key` and shows each shift live (with colors and a delay). Which would you like next?
