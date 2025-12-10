Below are **Stack implementations** in **C, C++, Java, Python**, and a **Tkinter GUI** simulation.
All support: **push, pop, peek, isEmpty, size** ✔

---

## ✅ 1️⃣ C Program – Stack using Array

```c
#include <stdio.h>
#define MAX 5

int stack[MAX];
int top = -1;

void push(int x) {
    if(top == MAX - 1) {
        printf("Stack Overflow\n");
    } else {
        stack[++top] = x;
        printf("%d pushed\n", x);
    }
}

int pop() {
    if(top == -1) {
        printf("Stack Underflow\n");
        return -1;
    }
    return stack[top--];
}

int peek() {
    if(top == -1) {
        printf("Stack is empty\n");
        return -1;
    }
    return stack[top];
}

int isEmpty() {
    return top == -1;
}

int size() {
    return top + 1;
}

int main() {
    push(10);
    push(20);
    printf("Top = %d\n", peek());
    printf("Popped = %d\n", pop());
    printf("Size = %d\n", size());
    return 0;
}
```

---

## ✅ 2️⃣ C++ Program – Stack using STL

```cpp
#include <iostream>
#include <stack>
using namespace std;

int main() {
    stack<int> st;
    st.push(10);
    st.push(20);

    cout << "Top: " << st.top() << endl;
    cout << "Size: " << st.size() << endl;

    st.pop();
    cout << "After pop, Top: " << st.top() << endl;
    cout << "Is Empty: " << (st.empty() ? "Yes" : "No") << endl;
    return 0;
}
```

---

## ✅ 3️⃣ Java Program – Stack using Array

```java
class Stack {
    int MAX = 5;
    int top = -1;
    int[] stack = new int[MAX];

    void push(int x) {
        if(top == MAX - 1)
            System.out.println("Stack Overflow");
        else
            stack[++top] = x;
    }

    int pop() {
        if(top == -1) {
            System.out.println("Stack Underflow");
            return -1;
        }
        return stack[top--];
    }

    int peek() {
        if(top == -1) return -1;
        return stack[top];
    }

    boolean isEmpty() {
        return top == -1;
    }

    int size() {
        return top + 1;
    }

    public static void main(String[] args) {
        Stack s = new Stack();
        s.push(10);
        s.push(20);
        System.out.println("Top: " + s.peek());
        System.out.println("Popped: " + s.pop());
        System.out.println("Size: " + s.size());
    }
}
```

---

## ✅ 4️⃣ Python Program – Stack using List

```python
class Stack:
    def __init__(self):
        self.stack = []

    def push(self, x):
        self.stack.append(x)

    def pop(self):
        if self.isEmpty():
            print("Stack Underflow")
            return None
        return self.stack.pop()

    def peek(self):
        if self.isEmpty():
            return None
        return self.stack[-1]

    def isEmpty(self):
        return len(self.stack) == 0

    def size(self):
        return len(self.stack)


s = Stack()
s.push(10)
s.push(20)
print("Top:", s.peek())
print("Popped:", s.pop())
print("Size:", s.size())
```

---

## ✅ 5️⃣ Python Tkinter – Stack GUI Simulation

📌 Buttons: Push, Pop, Peek, Size, Clear
📌 Shows real-time stack content on screen

```python
import tkinter as tk
from tkinter import messagebox

class StackGUI:
    def __init__(self, root):
        self.stack = []
        self.root = root
        root.title("Stack Implementation")

        self.entry = tk.Entry(root, width=20)
        self.entry.pack(pady=5)

        tk.Button(root, text="Push", command=self.push).pack(fill='x')
        tk.Button(root, text="Pop", command=self.pop).pack(fill='x')
        tk.Button(root, text="Peek", command=self.peek).pack(fill='x')
        tk.Button(root, text="Size", command=self.size).pack(fill='x')
        tk.Button(root, text="Clear", command=self.clear).pack(fill='x')

        self.display = tk.Label(root, text="Stack: []", font=("Arial", 14))
        self.display.pack(pady=10)

    def update_display(self):
        self.display.config(text=f"Stack: {self.stack}")

    def push(self):
        val = self.entry.get()
        if val:
            self.stack.append(val)
            self.update_display()
            self.entry.delete(0, tk.END)

    def pop(self):
        if self.stack:
            val = self.stack.pop()
            messagebox.showinfo("Popped", val)
            self.update_display()
        else:
            messagebox.showerror("Error", "Stack is empty")

    def peek(self):
        if self.stack:
            messagebox.showinfo("Top Element", self.stack[-1])
        else:
            messagebox.showerror("Error", "Stack is empty")

    def size(self):
        messagebox.showinfo("Size", len(self.stack))

    def clear(self):
        self.stack.clear()
        self.update_display()


root = tk.Tk()
app = StackGUI(root)
root.mainloop()
```

---

If you want, I can also give:

✔ Animated Tkinter version
✔ Stack using Linked List in all languages
✔ Push/Pop step-by-step diagrams for DSA notes
✔ PDF/Word format for assignment submission

Would you like a **Queue** implementation next? 🚀
