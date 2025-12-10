Here are **Queue implementations with all required operations**
(Enqueue, Dequeue, Peek, isEmpty, Size) in **C, C++, Java, Python**

* **Tkinter GUI simulation**.

---

## ✅ 1️⃣ C Program – Queue using Array

```c
#include <stdio.h>
#define MAX 5

int queue[MAX];
int front = -1, rear = -1;

void enqueue(int data) {
    if (rear == MAX - 1) {
        printf("Queue Overflow\n");
        return;
    }
    if (front == -1) front = 0;
    queue[++rear] = data;
    printf("%d enqueued\n", data);
}

int dequeue() {
    if (front == -1 || front > rear) {
        printf("Queue Underflow\n");
        return -1;
    }
    return queue[front++];
}

int peek() {
    if (front == -1 || front > rear) {
        printf("Queue is Empty\n");
        return -1;
    }
    return queue[front];
}

int isEmpty() {
    return (front == -1 || front > rear);
}

int size() {
    if (isEmpty()) return 0;
    return (rear - front + 1);
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);

    printf("Dequeued: %d\n", dequeue());
    printf("Peek: %d\n", peek());
    printf("Size: %d\n", size());
    return 0;
}
```

---

## ✅ 2️⃣ C++ Program – Queue using STL

```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() {
    queue<int> q;

    q.push(10); // Enqueue
    q.push(20);
    q.push(30);

    cout << "Front: " << q.front() << endl; // Peek

    cout << "Dequeued: " << q.front() << endl;
    q.pop(); // Dequeue

    cout << "Size: " << q.size() << endl;

    cout << (q.empty() ? "Queue Empty" : "Queue Not Empty");
    return 0;
}
```

---

## ✅ 3️⃣ Java Program – Queue using LinkedList

```java
import java.util.*;

public class QueueDemo {
    public static void main(String[] args) {
        Queue<Integer> q = new LinkedList<>();

        q.add(10); // Enqueue
        q.add(20);
        q.add(30);

        System.out.println("Front: " + q.peek()); // Peek
        System.out.println("Dequeued: " + q.remove()); // Dequeue
        System.out.println("Size: " + q.size());
        System.out.println(q.isEmpty() ? "Queue Empty" : "Queue Not Empty");
    }
}
```

---

## ✅ 4️⃣ Python Program – Queue using list

```python
class Queue:
    def __init__(self):
        self.q = []

    def enqueue(self, data):
        self.q.append(data)
        print(f"{data} enqueued")

    def dequeue(self):
        if self.is_empty():
            print("Queue Underflow")
            return None
        return self.q.pop(0)

    def peek(self):
        return None if self.is_empty() else self.q[0]

    def is_empty(self):
        return len(self.q) == 0

    def size(self):
        return len(self.q)


queue = Queue()
queue.enqueue(10)
queue.enqueue(20)
queue.enqueue(30)

print("Dequeued:", queue.dequeue())
print("Peek:", queue.peek())
print("Size:", queue.size())
```

---

## 🎨 5️⃣ Tkinter Queue Simulation

This GUI demonstrates enqueue, dequeue, display visually.

```python
import tkinter as tk
from tkinter import messagebox

class QueueGUI:
    def __init__(self):
        self.q = []

        self.win = tk.Tk()
        self.win.title("Queue Simulation")

        tk.Label(self.win, text="Enter Value").pack()
        self.entry = tk.Entry(self.win)
        self.entry.pack()

        tk.Button(self.win, text="Enqueue", command=self.enqueue).pack(pady=3)
        tk.Button(self.win, text="Dequeue", command=self.dequeue).pack(pady=3)

        self.display = tk.Label(self.win, text="Queue: []", font=("Arial", 14))
        self.display.pack(pady=10)

        self.win.mainloop()

    def enqueue(self):
        val = self.entry.get()
        if val == "":
            messagebox.showwarning("Warning", "Enter a value")
            return
        self.q.append(val)
        self.update()

    def dequeue(self):
        if len(self.q) == 0:
            messagebox.showerror("Error", "Queue is Empty!")
            return
        self.q.pop(0)
        self.update()

    def update(self):
        self.display.config(text=f"Queue: {self.q}")
        self.entry.delete(0, tk.END)


QueueGUI()
```

---

### Want circular queue / linked list queue / priority queue also?

Or full **step-by-step animation** in Tkinter? Let me know!
