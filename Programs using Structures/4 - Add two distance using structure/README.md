Here is your program **cleaned, corrected, and formatted** properly in **C** and **C++**.
Your logic is correct — only formatting and main return type adjusted.

---

# ✅ Corrected **C Program**

(Works in GCC / VS Code)

```c
#include <stdio.h>

struct Distance {
    int feet;
    float inch;
} d1, d2, sum;

int main() {
    printf("Enter information for 1st distance\n");
    printf("Enter feet: ");
    scanf("%d", &d1.feet);
    printf("Enter inch: ");
    scanf("%f", &d1.inch);

    printf("\nEnter information for 2nd distance\n");
    printf("Enter feet: ");
    scanf("%d", &d2.feet);
    printf("Enter inch: ");
    scanf("%f", &d2.inch);

    sum.feet = d1.feet + d2.feet;
    sum.inch = d1.inch + d2.inch;

    // Convert inches to feet if inches > 12
    if (sum.inch >= 12.0) {
        sum.inch -= 12.0;
        sum.feet++;
    }

    printf("\nSum of distances = %d' - %.1f\"\n", sum.feet, sum.inch);
    return 0;
}
```

---

# ✅ Corrected **C++ Program**

(with `iostream` instead of `stdio.h`)

```cpp
#include <iostream>
using namespace std;

struct Distance {
    int feet;
    float inch;
} d1, d2, sum;

int main() {
    cout << "Enter information for 1st distance\n";
    cout << "Enter feet: ";
    cin >> d1.feet;
    cout << "Enter inch: ";
    cin >> d1.inch;

    cout << "\nEnter information for 2nd distance\n";
    cout << "Enter feet: ";
    cin >> d2.feet;
    cout << "Enter inch: ";
    cin >> d2.inch;

    sum.feet = d1.feet + d2.feet;
    sum.inch = d1.inch + d2.inch;

    if (sum.inch >= 12.0) {
        sum.inch -= 12.0;
        sum.feet++;
    }

    cout << "\nSum of distances = " << sum.feet
         << "' - " << sum.inch << "\"\n";

    return 0;
}
```

---

### 📌 Sample Output

```
Enter information for 1st distance
Enter feet: 5
Enter inch: 8.5

Enter information for 2nd distance
Enter feet: 3
Enter inch: 6.7

Sum of distances = 9' - 3.2"
```

---

If you want, I can also give:
✔ Distance subtraction
✔ Distance comparison (largest)
✔ Using array of structures to add multiple distances

Would you like those too?
