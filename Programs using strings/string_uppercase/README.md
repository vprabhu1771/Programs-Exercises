```
#include <stdio.h>

void string_uppercase(char *data);

int main()
{
    char data[10];
    
    int i = 0;
    
    printf("Enter your name\n");
    
    scanf("%s", data);
    
    
    string_uppercase(data);

    return 0;
}

void string_uppercase(char *data)
{
    int i = 0;
    
    while(data[i] >= 97 && data[i] <= 122)
    {
        data[i] -= 32;
        
        i++;
    }
    
    printf("%s", data);
} 
```

Below are the **corrected C version** and the **C++, Java, Python, and Tkinter versions** of your `string_uppercase` program.

⚠️ **Important Correction**
Your loop is wrong:

```c
while(data[i] >= 97 && data[i] <= 122)   // ❌ wrong → stops when uppercase letter appears
```

You need:

```c
while (data[i] != '\0') {
    if (data[i] >= 'a' && data[i] <= 'z')
        data[i] -= 32;
    i++;
}
```

---

# ✅ Corrected **C Version**

```c
#include <stdio.h>

void string_uppercase(char *data);

int main()
{
    char data[10];

    printf("Enter your name\n");
    scanf("%s", data);

    string_uppercase(data);

    return 0;
}

void string_uppercase(char *data)
{
    int i = 0;

    while (data[i] != '\0')
    {
        if (data[i] >= 'a' && data[i] <= 'z')
        {
            data[i] -= 32;
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

void string_uppercase(char* data) {
    int i = 0;
    while (data[i] != '\0') {
        if (data[i] >= 'a' && data[i] <= 'z')
            data[i] -= 32;
        i++;
    }
}

int main() {
    char data[10];
    cout << "Enter your name\n";
    cin >> data;

    string_uppercase(data);
    cout << data;

    return 0;
}
```

---

# ✅ **Java Version**

```java
import java.util.Scanner;

public class Main {

    public static String toUppercase(String data) {
        char[] arr = data.toCharArray();

        for (int i = 0; i < arr.length; i++) {
            if (arr[i] >= 'a' && arr[i] <= 'z') {
                arr[i] -= 32;
            }
        }

        return new String(arr);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter your name");
        String input = sc.nextLine();

        System.out.println(toUppercase(input));
    }
}
```

---

# ✅ **Python Version**

```python
def string_uppercase(data):
    result = ""
    for ch in data:
        if 'a' <= ch <= 'z':
            result += chr(ord(ch) - 32)
        else:
            result += ch
    return result

name = input("Enter your name\n")
print(string_uppercase(name))
```

---

# ✅ **Tkinter GUI Version (Python)**

```python
import tkinter as tk

def string_uppercase(data):
    result = ""
    for ch in data:
        if 'a' <= ch <= 'z':
            result += chr(ord(ch) - 32)
        else:
            result += ch
    return result

def convert():
    text = entry.get()
    output_label.config(text="Uppercase: " + string_uppercase(text))

root = tk.Tk()
root.title("Uppercase Converter")
root.geometry("300x200")

tk.Label(root, text="Enter text:").pack(pady=5)
entry = tk.Entry(root, width=25)
entry.pack(pady=5)

tk.Button(root, text="Convert", command=convert).pack(pady=10)

output_label = tk.Label(root, text="Uppercase: ")
output_label.pack(pady=10)

root.mainloop()
```

---

If you need **toggle case**, **title case**, **string reverse**, or **count lowercase/uppercase**, tell me!
