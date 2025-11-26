```
#include <stdio.h>

int is_alphabet(char data);

int main()
{
    printf("%d", is_alphabet('a'));

    return 0;
}

int is_alphabet(char data)
{
    if(data >= 65 && data <= 90 || data >= 97 && data <= 122)
    {
        return 1;
    }
    else
    {
        return -1;
    }
}
```

Below is your **alphabet checking program** rewritten cleanly in **C**, **C++**, **Java**, **Python**, and **Tkinter GUI**.

Your logic is correct — just missing parentheses for clarity.

---

# ✅ **C Version (clean & correct)**

```c
#include <stdio.h>

int is_alphabet(char data);

int main()
{
    printf("%d", is_alphabet('a'));
    return 0;
}

int is_alphabet(char data)
{
    if ((data >= 'A' && data <= 'Z') || (data >= 'a' && data <= 'z'))
        return 1;
    else
        return -1;
}
```

✔ Using `'A'`, `'Z'`, `'a'`, `'z'` makes code more readable.

---

# ✅ **C++ Version**

```cpp
#include <iostream>
using namespace std;

int is_alphabet(char data) {
    if ((data >= 'A' && data <= 'Z') || (data >= 'a' && data <= 'z'))
        return 1;
    return -1;
}

int main() {
    cout << is_alphabet('a');
    return 0;
}
```

---

# ✅ **Java Version**

```java
public class AlphabetCheck {

    static int isAlphabet(char ch) {
        if ((ch >= 'A' && ch <= 'Z') || (ch >= 'a' && ch <= 'z'))
            return 1;
        return -1;
    }

    public static void main(String[] args) {
        System.out.println(isAlphabet('a'));
    }
}
```

---

# ✅ **Python Version**

```python
def is_alphabet(ch):
    if ('A' <= ch <= 'Z') or ('a' <= ch <= 'z'):
        return 1
    return -1

print(is_alphabet('a'))
```

---

# ✅ **Tkinter Version (Python GUI)**

This GUI lets the user type a character and checks if it is an alphabet.

```python
import tkinter as tk

def check_alphabet():
    ch = entry.get()
    if len(ch) != 1:
        result.config(text="Enter 1 character only.")
        return

    if ('A' <= ch <= 'Z') or ('a' <= ch <= 'z'):
        result.config(text="Alphabet (1)")
    else:
        result.config(text="Not Alphabet (-1)")

root = tk.Tk()
root.title("Alphabet Checker")

tk.Label(root, text="Enter a character:").pack()

entry = tk.Entry(root)
entry.pack()

tk.Button(root, text="Check", command=check_alphabet).pack()

result = tk.Label(root, text="")
result.pack()

root.mainloop()
```

---

If you want, I can also give:

✅ Tkinter version with color indicators
✅ Version that checks vowel/consonant
✅ Version that checks digit/special character

Just tell me!

