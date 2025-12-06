Below are **corrected Pattern Replacement programs** for
**C, C++, Java, and Python** ✔️

Your original C code had issues:

* Smart quotes (“ ”) ❌
* Unsafe `gets()` ❌ → replaced using `fgets()`
* Missing string termination
* Extra character copied after replacement — logic fixed

---

## ✅ 1️⃣ C Program — Replace Pattern in String (Manual)

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[200], pat[20], rep_pat[100], new_str[300];
    int i = 0, j = 0, k, n = 0, rep;

    printf("Enter source string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';

    printf("Enter pattern to replace: ");
    fgets(pat, sizeof(pat), stdin);
    pat[strcspn(pat, "\n")] = '\0';

    printf("Enter replacement string: ");
    fgets(rep_pat, sizeof(rep_pat), stdin);
    rep_pat[strcspn(rep_pat, "\n")] = '\0';

    while (str[i] != '\0') {
        j = 0;
        k = i;

        while (str[k] == pat[j] && pat[j] != '\0') {
            k++;
            j++;
        }

        if (pat[j] == '\0') {  // Found match
            rep = 0;
            while (rep_pat[rep] != '\0') {
                new_str[n++] = rep_pat[rep++];
            }
            i = k;
        } else {
            new_str[n++] = str[i++];
        }
    }

    new_str[n] = '\0'; // terminate

    printf("\nResult: %s\n", new_str);
    return 0;
}
```

---

## 🟦 2️⃣ C++ Program

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main() {
    char str[200], pat[20], rep_pat[100], new_str[300];
    int i = 0, j, k, n = 0;

    cout << "Enter source string: ";
    cin.getline(str, 200);
    cout << "Enter pattern to replace: ";
    cin.getline(pat, 20);
    cout << "Enter replacement string: ";
    cin.getline(rep_pat, 100);

    while (str[i] != '\0') {
        j = 0;
        k = i;

        while (str[k] == pat[j] && pat[j] != '\0') {
            k++; j++;
        }

        if (pat[j] == '\0') {
            for (int r = 0; rep_pat[r] != '\0'; r++)
                new_str[n++] = rep_pat[r];
            i = k;
        } else {
            new_str[n++] = str[i++];
        }
    }

    new_str[n] = '\0';
    cout << "\nResult: " << new_str << endl;
    return 0;
}
```

---

## ☕ 3️⃣ Java Program

```java
import java.util.Scanner;

public class PatternReplace {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter source string: ");
        String str = sc.nextLine();

        System.out.print("Enter pattern to replace: ");
        String pat = sc.nextLine();

        System.out.print("Enter replacement string: ");
        String rep = sc.nextLine();

        String result = "";
        int i = 0;

        while (i < str.length()) {
            if (i + pat.length() <= str.length() &&
                str.substring(i, i + pat.length()).equals(pat)) {

                result += rep;
                i += pat.length();
            } else {
                result += str.charAt(i);
                i++;
            }
        }

        System.out.println("\nResult: " + result);
        sc.close();
    }
}
```

---

## 🐍 4️⃣ Python Program

```python
src = input("Enter source string: ")
pat = input("Enter pattern to replace: ")
rep = input("Enter replacement string: ")

result = ""
i = 0

while i < len(src):
    # check substring match
    if src[i:i+len(pat)] == pat:
        result += rep
        i += len(pat)
    else:
        result += src[i]
        i += 1

print("\nResult:", result)
```

---

### Want GUI for this?

✔ Python Tkinter version available if you want it
✔ Also can support **case-insensitive** replace
✔ Replace **all / first / last** occurrences

Tell me if you want enhancements!
