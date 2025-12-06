Below are **corrected programs** for **Finding vowels and detecting consecutive vowels**
in **C, C++, Java, Python & Tkinter** ✔️

Your original C code issues fixed:

* Removed `gets()` (unsafe)
* Removed `clrscr()` (non-standard)
* Fixed logic for vowel check
* Included uppercase vowels
* Improved output formatting

---

## ✅ 1️⃣ C Program — Consecutive Vowel Detection

```c
#include <stdio.h>
#include <string.h>

int isVowel(char ch) {
    ch = (ch >= 'A' && ch <= 'Z') ? ch + 32 : ch; // convert to lowercase
    return (ch=='a'||ch=='e'||ch=='i'||ch=='o'||ch=='u');
}

int main() {
    char a[80];
    int i, n, found = 0, vowelFound = 0;

    printf("Enter a string: ");
    fgets(a, sizeof(a), stdin);
    a[strcspn(a, "\n")] = '\0';

    n = strlen(a);
    
    for(i = 0; i < n - 1; i++) {
        if(isVowel(a[i])) vowelFound = 1;
        if(isVowel(a[i]) && isVowel(a[i+1])) {
            printf("Consecutive vowels '%c%c' found at position %d\n",
                   a[i], a[i+1], i + 1);
            found = 1;
        }
    }

    if(!found) {
        if(vowelFound)
            printf("Vowels found, but not consecutively.\n");
        else
            printf("No vowels found in the string.\n");
    }

    return 0;
}
```

---

## 🟦 2️⃣ C++ Program

```cpp
#include <iostream>
#include <cstring>
using namespace std;

bool isVowel(char ch) {
    ch = tolower(ch);
    return ch=='a'||ch=='e'||ch=='i'||ch=='o'||ch=='u';
}

int main() {
    char a[80];
    cout << "Enter string: ";
    cin.getline(a, 80);

    int n = strlen(a), found = 0, vowelFound = 0;

    for(int i = 0; i < n-1; i++) {
        if(isVowel(a[i])) vowelFound = 1;
        if(isVowel(a[i]) && isVowel(a[i+1])) {
            cout << "Consecutive vowels '" << a[i] << a[i+1]
                 << "' found at position " << i+1 << endl;
            found = 1;
        }
    }

    if(!found) {
        if(vowelFound)
            cout << "Vowels found, but not consecutively.\n";
        else
            cout << "No vowels found.\n";
    }
    return 0;
}
```

---

## ☕ 3️⃣ Java Program

```java
import java.util.Scanner;

public class VowelCheck {
    static boolean isVowel(char ch) {
        ch = Character.toLowerCase(ch);
        return "aeiou".indexOf(ch) != -1;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a string: ");
        String s = sc.nextLine();
        boolean found = false, vowelFound = false;

        for(int i = 0; i < s.length() - 1; i++) {
            if(isVowel(s.charAt(i))) vowelFound = true;
            if(isVowel(s.charAt(i)) && isVowel(s.charAt(i+1))) {
                System.out.println("Consecutive vowels '" +
                                  s.charAt(i) + s.charAt(i+1) +
                                  "' found at position " + (i+1));
                found = true;
            }
        }

        if(!found) {
            if(vowelFound)
                System.out.println("Vowels found but not consecutively.");
            else
                System.out.println("No vowels found.");
        }
        sc.close();
    }
}
```

---

## 🐍 4️⃣ Python Program

```python
s = input("Enter a string: ")

vowels = "aeiouAEIOU"
found = False
vowelFound = False

for i in range(len(s) - 1):
    if s[i] in vowels:
        vowelFound = True
    if s[i] in vowels and s[i+1] in vowels:
        print(f"Consecutive vowels '{s[i]}{s[i+1]}' found at position {i+1}")
        found = True

if not found:
    if vowelFound:
        print("Vowels found but not consecutively.")
    else:
        print("No vowels found.")
```

---

## 🖥️ 5️⃣ Python Tkinter GUI Program

```python
import tkinter as tk

def check_vowels():
    s = entry.get()
    vowels = "aeiouAEIOU"
    result = ""
    found = False
    vowelFound = False

    for i in range(len(s) - 1):
        if s[i] in vowels:
            vowelFound = True
        if s[i] in vowels and s[i+1] in vowels:
            result += f"Consecutive vowels '{s[i]}{s[i+1]}' at position {i+1}\n"
            found = True

    if not found:
        if vowelFound:
            result = "Vowels found but not consecutively."
        else:
            result = "No vowels found."

    output.config(text=result)

root = tk.Tk()
root.title("Vowel Checker")

tk.Label(root, text="Enter string:").pack()
entry = tk.Entry(root, width=40)
entry.pack(pady=10)

tk.Button(root, text="Check", command=check_vowels).pack(pady=10)

output = tk.Label(root, text="", font=("Arial", 12))
output.pack(pady=10)

root.mainloop()
```

---

### Want improvements?

✔ Highlight vowel positions
✔ Count total vowels
✔ Ignore spaces or punctuation

Tell me if you want extended features!
