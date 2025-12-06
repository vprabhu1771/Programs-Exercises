Here are the corrected and clean programs in **C, C++, Java, and Python** to find the **frequency of a character in a string**.

---

## ✅ **C Program**

> Issue fixed: After `gets()`, we need to clear buffer before reading character.

```c
#include <stdio.h>

int main() {
    char str[1000], ch;
    int i, count = 0;

    printf("Enter a string: ");
    scanf("%[^\n]", str);   // safer than gets()

    getchar(); // clear newline from buffer

    printf("Enter a character to find frequency: ");
    scanf("%c", &ch);

    for (i = 0; str[i] != '\0'; i++) {
        if (str[i] == ch)
            count++;
    }

    printf("Frequency of %c = %d\n", ch, count);
    return 0;
}
```

---

## ✅ **C++ Program**

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string str;
    char ch;
    int count = 0;

    cout << "Enter a string: ";
    getline(cin, str);

    cout << "Enter a character to find frequency: ";
    cin >> ch;

    for (char c : str) {
        if (c == ch)
            count++;
    }

    cout << "Frequency of " << ch << " = " << count << endl;
    return 0;
}
```

---

## ✅ **Java Program**

```java
import java.util.Scanner;

public class FrequencyOfChar {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a string: ");
        String str = sc.nextLine();

        System.out.print("Enter a character to find frequency: ");
        char ch = sc.next().charAt(0);

        int count = 0;
        for (int i = 0; i < str.length(); i++) {
            if (str.charAt(i) == ch)
                count++;
        }

        System.out.println("Frequency of " + ch + " = " + count);
    }
}
```

---

## ✅ **Python Program**

```python
string = input("Enter a string: ")
ch = input("Enter a character to find frequency: ")

count = string.count(ch)

print(f"Frequency of '{ch}' = {count}")
```

---

If you want, I can also provide the **Tkinter GUI version** for this program. Just tell me!
