Below are **Sorting strings in alphabetical order** programs in **C, C++, Java, Python & Tkinter GUI** — all equivalent to your logic.

---

## ✅ **C Program – Sort Strings Alphabetically**

```c
#include <stdio.h>
#include <string.h>

void main() {
    int i, j, n;
    char a[10][20], t[20];

    printf("Enter the number of strings: ");
    scanf("%d", &n);

    printf("Enter %d strings:\n", n);
    for(i = 0; i < n; i++)
        scanf("%s", a[i]);

    for(i = 0; i < n-1; i++)
        for(j = 0; j < n-1-i; j++)
            if(strcmp(a[j], a[j+1]) > 0) {
                strcpy(t, a[j]);
                strcpy(a[j], a[j+1]);
                strcpy(a[j+1], t);
            }

    printf("\nStrings after sorting:\n");
    for(i = 0; i < n; i++)
        printf("%s\n", a[i]);
}
```

---

## ✅ **C++ Program**

```cpp
#include <iostream>
#include <algorithm>
using namespace std;

int main() {
    int n;
    cout << "Enter number of strings: ";
    cin >> n;

    string a[n];
    cout << "Enter strings:\n";
    for(int i = 0; i < n; i++)
        cin >> a[i];

    sort(a, a + n);

    cout << "\nStrings after sorting:\n";
    for(int i = 0; i < n; i++)
        cout << a[i] << endl;
}
```

---

## ✅ **Java Program**

```java
import java.util.*;

public class SortStrings {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of strings: ");
        int n = sc.nextInt();
        String[] arr = new String[n];

        System.out.println("Enter strings:");
        for(int i = 0; i < n; i++)
            arr[i] = sc.next();

        Arrays.sort(arr);

        System.out.println("\nStrings after sorting:");
        for(String s : arr)
            System.out.println(s);
    }
}
```

---

## ✅ **Python Program**

```python
n = int(input("Enter number of strings: "))
arr = []

print("Enter strings:")
for _ in range(n):
    arr.append(input())

arr.sort()

print("\nStrings after sorting:")
for s in arr:
    print(s)
```

---

## ✅ **Tkinter GUI Program – Sort Strings Alphabetically**

```python
import tkinter as tk
from tkinter import messagebox

def sort_strings():
    text = entry.get("1.0", "end").strip().split()
    text.sort()
    result.delete("1.0", "end")
    for s in text:
        result.insert("end", s + "\n")

win = tk.Tk()
win.title("String Sorter")

tk.Label(win, text="Enter strings separated by space:").pack()

entry = tk.Text(win, height=5, width=40)
entry.pack()

tk.Button(win, text="Sort", command=sort_strings).pack(pady=10)

tk.Label(win, text="Sorted strings:").pack()

result = tk.Text(win, height=5, width=40)
result.pack()

win.mainloop()
```

---

### If you want, I can also:

✔ Add case-insensitive sorting
✔ Sort in descending order
✔ Add UI validations (empty input, numbers not allowed)

Would you like **ascending + descending** button in Tkinter?
