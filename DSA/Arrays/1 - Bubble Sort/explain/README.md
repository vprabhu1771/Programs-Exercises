# Step-by-step walkthrough — Bubble Sort on `[7, 12, 9, 11, 3]`

I'll show every comparison, whether we swap, and the array state after each swap. Bubble sort makes `n-1` passes (here `n=5`, so 4 passes). On pass `i` we compare pairs `j = 0 .. n-i-2`.

**Initial array:**
`[7, 12, 9, 11, 3]`

---

## Pass 1 (compare indices j = 0..3)

1. Compare `arr[0]` and `arr[1]` → `7` and `12`
   `7 > 12 ?` → **No swap**.
   Array: `[7, 12, 9, 11, 3]`

2. Compare `arr[1]` and `arr[2]` → `12` and `9`
   `12 > 9 ?` → **Yes, swap.**
   After swap: `[7, 9, 12, 11, 3]`

3. Compare `arr[2]` and `arr[3]` → `12` and `11`
   `12 > 11 ?` → **Yes, swap.**
   After swap: `[7, 9, 11, 12, 3]`

4. Compare `arr[3]` and `arr[4]` → `12` and `3`
   `12 > 3 ?` → **Yes, swap.**
   After swap: `[7, 9, 11, 3, 12]`

**End of Pass 1:** largest element `12` has "bubbled" to the end.
Array: `[7, 9, 11, 3, 12]`

---

## Pass 2 (compare indices j = 0..2)

1. Compare `arr[0]` and `arr[1]` → `7` and `9`
   `7 > 9 ?` → **No swap.**
   Array: `[7, 9, 11, 3, 12]`

2. Compare `arr[1]` and `arr[2]` → `9` and `11`
   `9 > 11 ?` → **No swap.**
   Array: `[7, 9, 11, 3, 12]`

3. Compare `arr[2]` and `arr[3]` → `11` and `3`
   `11 > 3 ?` → **Yes, swap.**
   After swap: `[7, 9, 3, 11, 12]`

**End of Pass 2:** second-largest `11` is now in position `n-2`.
Array: `[7, 9, 3, 11, 12]`

---

## Pass 3 (compare indices j = 0..1)

1. Compare `arr[0]` and `arr[1]` → `7` and `9`
   `7 > 9 ?` → **No swap.**
   Array: `[7, 9, 3, 11, 12]`

2. Compare `arr[1]` and `arr[2]` → `9` and `3`
   `9 > 3 ?` → **Yes, swap.**
   After swap: `[7, 3, 9, 11, 12]`

**End of Pass 3:** third-largest `9` in correct place.
Array: `[7, 3, 9, 11, 12]`

---

## Pass 4 (compare indices j = 0..0)

1. Compare `arr[0]` and `arr[1]` → `7` and `3`
   `7 > 3 ?` → **Yes, swap.**
   After swap: `[3, 7, 9, 11, 12]`

**End of Pass 4:** array is now sorted.
Final array: `[3, 7, 9, 11, 12]`

---

## Summary / Metrics

* Total comparisons performed: `4 + 3 + 2 + 1 = 10` (which equals `n*(n-1)/2` for `n=5` in the simple unoptimized version).
* Total swaps performed: `3` (pass1) + `1` (pass2) + `1` (pass3) + `1` (pass4) = **6 swaps**.
* Sorted output: `[3, 7, 9, 11, 12]`.

---

### Quick note

An optimized bubble sort stops early if a pass makes **0 swaps** (because the array is already sorted). In this example every pass had at least one swap until the last needed pass, so early termination wouldn't have happened before Pass 4.

Would you like the same step-by-step but printed out by the Python code (so you can see each comparison and swap live), or a visual animation (Tkinter) that highlights the swapped elements?
