```
#include <stdio.h>

void string_lowercase(char *data);

int main()
{
    char data[10];
    
    int i = 0;
    
    printf("Enter your name\n");
    
    scanf("%s", data);
    
    
    string_lowercase(data);

    return 0;
}

void string_lowercase(char *data)
{
    int i = 0;
    
    while(data[i] >= 65 && data[i] <= 97)
    {
        data[i] += 32;
        
        i++;
    }
    
    printf("%s", data);
}   
```

Below are the **corrected C version** and the **C++, Java, Python, and Tkinter GUI versions** of your `string_lowercase` program.

⚠️ **Important Correction**
Your loop condition is wrong:

```c
while(data[i] >= 65 && data[i] <= 97)   // ❌ wrong (65–90 uppercases, not 97)
```

Correct uppercase ASCII range:

* `'A' = 65`
* `'Z' = 90`

So condition must be:

```c
while(data[i] != '\0')
{
    if(data[i] >= 'A' && data[i] <= 'Z')
        data[i] += 32;
    i++;
}
```

---

# ✅ Corrected **C** Code (Fix Included)

```c
#include <stdio.h>

void string_lowercase(char *data);

int main()
{
    char data[10];
    
    printf("Enter your name\n");
    scanf("%s", data);
    
    string_lowercase(data);

    return 0;
}

void string_lowercase(char *data)
{
    int i = 0;
    
    while (data[i] != '\0')
    {
        if (data[i] >= 'A' && data[i] <= 'Z')
        {
            data[i] += 32;
        }
        i++;
    }
    
    printf("%s", data);
}
```

---

# ✅ **C++ Version**

```cpp
#include <iostream>
using namespace std;

void string_lowercase(char *data) {
    int i = 0;
    while (data[i] != '\0') {
        if (data[i] >= 'A' && data[i] <= 'Z')
            data[i] += 32;
        i++;
    }
}

int main() {
    char data[10];
    cout << "Enter your name\n";
    cin >> data;

    string_lowercase(data);
    cout << data;

    return 0;
}
```

---

# ✅ **Java Version**

```java
import java.util.Scanner;

public class Main {

    public static String toLowercase(String data) {
        char[] chars = data.toCharArray();
        
        for (int i = 0; i < chars.length; i++) {
            if (chars[i] >= 'A' && chars[i] <= 'Z') {
                chars[i] += 32;
            }
        }
        
        return new String(chars);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter your name");
        String input = sc.nextLine();

        System.out.println(toLowercase(input));
    }
}
```

---

# ✅ **Python Version**

```python
def string_lowercase(data):
    result = ""
    for ch in data:
        if 'A' <= ch <= 'Z':
            result += chr(ord(ch) + 32)
        else:
            result += ch
    return result

name = input("Enter your name\n")
print(string_lowercase(name))
```

---

# ✅ **Tkinter GUI Version (Python)**

```python
import tkinter as tk

def string_lowercase(data):
    result = ""
    for ch in data:
        if 'A' <= ch <= 'Z':
            result += chr(ord(ch) + 32)
        else:
            result += ch
    return result

def convert():
    text = entry.get()
    output_label.config(text="Lowercase: " + string_lowercase(text))

root = tk.Tk()
root.title("Lowercase Converter")
root.geometry("300x200")

tk.Label(root, text="Enter text:").pack(pady=5)
entry = tk.Entry(root, width=25)
entry.pack(pady=5)

tk.Button(root, text="Convert", command=convert).pack(pady=10)
output_label = tk.Label(root, text="Lowercase: ")
output_label.pack(pady=10)

root.mainloop()
```

---

If you want **uppercase converter**, **toggle case**, or **real-time conversion**, just tell me!
