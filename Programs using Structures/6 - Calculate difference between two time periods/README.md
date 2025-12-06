Here is your program **corrected, formatted, and provided in both C & C++**.
Your logic is correct — only `void main()` is replaced with `int main()` (standard), formatting improved.

---

## ✅ Corrected **C Program**

```c
#include <stdio.h>

struct TIME {
    int seconds;
    int minutes;
    int hours;
};

void Difference(struct TIME t1, struct TIME t2, struct TIME *diff);

int main() {
    struct TIME t1, t2, diff;

    printf("Enter start time: \n");
    printf("Enter hours, minutes and seconds respectively: ");
    scanf("%d %d %d", &t1.hours, &t1.minutes, &t1.seconds);

    printf("Enter stop time: \n");
    printf("Enter hours, minutes and seconds respectively: ");
    scanf("%d %d %d", &t2.hours, &t2.minutes, &t2.seconds);

    Difference(t1, t2, &diff);

    printf("\nTIME DIFFERENCE: %02d:%02d:%02d - %02d:%02d:%02d",
           t1.hours, t1.minutes, t1.seconds,
           t2.hours, t2.minutes, t2.seconds);

    printf(" = %02d:%02d:%02d\n",
           diff.hours, diff.minutes, diff.seconds);

    return 0;
}

void Difference(struct TIME t1, struct TIME t2, struct TIME *differ) {
    if (t2.seconds > t1.seconds) {
        --t1.minutes;
        t1.seconds += 60;
    }
    differ->seconds = t1.seconds - t2.seconds;

    if (t2.minutes > t1.minutes) {
        --t1.hours;
        t1.minutes += 60;
    }
    differ->minutes = t1.minutes - t2.minutes;

    differ->hours = t1.hours - t2.hours;
}
```

---

## ✅ Corrected **C++ Program**

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

struct TIME {
    int hours;
    int minutes;
    int seconds;
};

void Difference(TIME t1, TIME t2, TIME &diff) {
    if (t2.seconds > t1.seconds) {
        t1.minutes--;
        t1.seconds += 60;
    }
    diff.seconds = t1.seconds - t2.seconds;

    if (t2.minutes > t1.minutes) {
        t1.hours--;
        t1.minutes += 60;
    }
    diff.minutes = t1.minutes - t2.minutes;

    diff.hours = t1.hours - t2.hours;
}

int main() {
    TIME t1, t2, diff;

    cout << "Enter start time:\n";
    cout << "Enter hours, minutes, seconds: ";
    cin >> t1.hours >> t1.minutes >> t1.seconds;

    cout << "Enter stop time:\n";
    cout << "Enter hours, minutes, seconds: ";
    cin >> t2.hours >> t2.minutes >> t2.seconds;

    Difference(t1, t2, diff);

    cout << "\nTIME DIFFERENCE: ";
    cout << setfill('0') << setw(2) << t1.hours << ":"
         << setw(2) << t1.minutes << ":"
         << setw(2) << t1.seconds;

    cout << " - "
         << setw(2) << t2.hours << ":"
         << setw(2) << t2.minutes << ":"
         << setw(2) << t2.seconds;

    cout << " = "
         << setw(2) << diff.hours << ":"
         << setw(2) << diff.minutes << ":"
         << setw(2) << diff.seconds << endl;

    return 0;
}
```

---

### 📌 Example Input

```
Enter start time:
10 45 55
Enter stop time:
8 50 20
```

### 📌 Output

```
TIME DIFFERENCE: 10:45:55 - 08:50:20 = 01:55:35
```

---

If you want, I can also provide:
✔ Validation for invalid time values
✔ Accept time in HH:MM:SS format
✔ Multiply or add multiple time values

Would you like any enhancements?
