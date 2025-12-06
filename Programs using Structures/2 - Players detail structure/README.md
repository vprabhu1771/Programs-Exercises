Your logic has **multiple critical errors**. Let me explain and give you **fully corrected C & C++ programs**.

---

## ❌ Problems in your Program

| Issue                                                 | Effect                                                  |
| ----------------------------------------------------- | ------------------------------------------------------- |
| Sorting loop `i < n` and using `i+1`                  | Last index goes **out of range** → runtime error        |
| Sorting only **avg_run**, not the whole player record | Data becomes mismatched (name/age do not move with avg) |
| Sorting logic wrong                                   | Only ONE pass → **no proper sorting**                   |
| Integer division: `run/nmatch`                        | Wrong average (use float)                               |
| `clrscr()` + `<conio.h>` not standard                 | Works only in TurboC                                    |

---

## ✔ Corrected Version — **C Program**

👉 Includes **Bubble Sort** and correct average calculation.

```c
#include <stdio.h>

struct play {
    char name[25];
    int age;
    int nmatch;
    int run;
    float avgrun;
} cri[100];

int main() {
    int n, i, j;
    struct play temp;

    printf("Enter number of players: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++) {
        printf("\nEnter Name, Age, Matches Played, Total Runs: ");
        scanf("%s %d %d %d",
              cri[i].name,
              &cri[i].age,
              &cri[i].nmatch,
              &cri[i].run);

        cri[i].avgrun = (float)cri[i].run / cri[i].nmatch;
    }

    // Bubble Sort based on avgrun (ascending)
    for(i = 0; i < n-1; i++) {
        for(j = 0; j < n-i-1; j++) {
            if(cri[j].avgrun > cri[j+1].avgrun) {
                temp = cri[j];
                cri[j] = cri[j+1];
                cri[j+1] = temp;
            }
        }
    }

    printf("\nDetails in Ascending Order of Average Runs\n");
    printf("\nName\tAge\tMatches\tRuns\tAvg Run");
    for(i = 0; i < n; i++) {
        printf("\n%s\t%d\t%d\t%d\t%.2f",
               cri[i].name,
               cri[i].age,
               cri[i].nmatch,
               cri[i].run,
               cri[i].avgrun);
    }

    return 0;
}
```

---

## ✔ Corrected Version — **C++ Program**

```cpp
#include <iostream>
#include <iomanip>
#include <string>
using namespace std;

struct play {
    string name;
    int age;
    int nmatch;
    int run;
    float avgrun;
} cri[100];

int main() {
    int n, i, j;
    play temp;

    cout << "Enter number of players: ";
    cin >> n;

    for(i = 0; i < n; i++) {
        cout << "\nEnter Name, Age, Matches, Total Runs: ";
        cin >> cri[i].name >> cri[i].age >> cri[i].nmatch >> cri[i].run;

        cri[i].avgrun = (float)cri[i].run / cri[i].nmatch;
    }

    for(i = 0; i < n-1; i++) {
        for(j = 0; j < n-i-1; j++) {
            if(cri[j].avgrun > cri[j+1].avgrun) {
                temp = cri[j];
                cri[j] = cri[j+1];
                cri[j+1] = temp;
            }
        }
    }

    cout << "\nDetails in Ascending Order of Average Runs\n";
    cout << "\nName\tAge\tMatches\tRuns\tAvg";
    for(i = 0; i < n; i++) {
        cout << "\n" << cri[i].name << "\t"
             << cri[i].age << "\t"
             << cri[i].nmatch << "\t"
             << cri[i].run << "\t"
             << fixed << setprecision(2) << cri[i].avgrun;
    }

    return 0;
}
```

---

### 🎯 What is Fixed?

✔ Correct average: `(float)run / matches`
✔ Proper sorting for **complete record**
✔ Protected array range
✔ Standard C / C++ — works in GCC, VS Code, CodeBlocks

---

If you want, I can also add:

* 🔹 Highest scorer result
* 🔹 Search a player by name
* 🔹 Save/Load player data using file handling

Would you like any of these upgrades?
