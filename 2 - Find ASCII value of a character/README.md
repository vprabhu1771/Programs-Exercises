# C
```c
#include<stdio.h>

#include<conio.h>

void main()
{
	char data

	clrscr();

	printf("Enter any character\n");

	scanf("%c", &data);

	printf("Character is %c\n", data);

	printf("ASCII is %d\n", data);

	getch();
}
```

# CPP

```cpp
#include <iostream>
#include <conio.h>  // For clrscr() and getch(), Turbo C++ specific

using namespace std;

int main() {
    char data;

    clrscr(); // Note: This works only in Turbo C++, not in modern compilers

    cout << "Enter any character: ";
    cin >> data;

    cout << "Character is: " << data << endl;
    cout << "ASCII is: " << static_cast<int>(data) << endl;

    getch(); // Pauses the output screen (Turbo C++ specific)
    return 0;
}
```

# Java 

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        char data;

        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter any character:");
        data = scanner.next().charAt(0);  // Read the first character of the input

        System.out.println("Character is: " + data);
        System.out.println("ASCII is: " + (int) data);  // Cast to int to get ASCII value

        scanner.close();
    }
}
```

# Python

```python
Here's the equivalent **Python** version of your C code:

```python
# Python program to read a character and print its ASCII value

data = input("Enter any character: ")[0]  # Get the first character of input

print("Character is:", data)
print("ASCII is:", ord(data))  # ord() gives ASCII value
```

### Explanation:

* `input()` reads a string; `[0]` ensures only the first character is used.
* `ord()` returns the ASCII value of a character.

Would you like a version that handles invalid input or multi-character strings gracefully?


# Tkinter

Here's the **Tkinter (GUI) version in Python** of your original C code that reads a character and displays its ASCII value:

```python
import tkinter as tk
from tkinter import messagebox

def show_ascii():
    text = entry.get()
    if text:
        char = text[0]  # Take only the first character
        ascii_value = ord(char)
        result = f"Character: {char}\nASCII: {ascii_value}"
        messagebox.showinfo("Result", result)
    else:
        messagebox.showwarning("Input Error", "Please enter a character.")

# Create the main window
root = tk.Tk()
root.title("Character to ASCII")
root.geometry("300x150")

# Label and entry
label = tk.Label(root, text="Enter any character:")
label.pack(pady=10)

entry = tk.Entry(root)
entry.pack()

# Button
button = tk.Button(root, text="Show ASCII", command=show_ascii)
button.pack(pady=10)

# Run the app
root.mainloop()
```

### Features:

* Simple GUI with a label, entry box, and a button.
* Uses `messagebox` to display the character and its ASCII value.

Would you like this app to support multiple characters and list ASCII values for all?

