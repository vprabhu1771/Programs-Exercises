Perfect 👍
Here is a **complete DSA guide for Doubly Linked List** with **C, C++, Java, Python** implementations and a **Tkinter visualization**, written in **exam + interview friendly style**.

---

# 🔗 DOUBLY LINKED LIST (DLL)

## 📌 What is a Doubly Linked List?

A **Doubly Linked List** is a linear data structure where each node contains:

* **Data**
* **Pointer to previous node**
* **Pointer to next node**

### Node Structure

```
[ prev | data | next ]
```

---

## ✅ Advantages

✔ Traversal in both directions
✔ Easy deletion of a given node
✔ Efficient insertion

## ❌ Disadvantages

❌ Extra memory for `prev` pointer
❌ Slightly complex than SLL

---

## ⏱ Time Complexity

| Operation           | Time |
| ------------------- | ---- |
| Insert at beginning | O(1) |
| Insert at end       | O(n) |
| Delete              | O(n) |
| Search              | O(n) |

---

# 💻 C Implementation (DLL)

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

void insert(struct Node** head, int value) {
    struct Node* newNode = malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->prev = NULL;
    newNode->next = *head;

    if (*head != NULL)
        (*head)->prev = newNode;

    *head = newNode;
}

void display(struct Node* head) {
    struct Node* temp = head;
    while (temp) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;
    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);
    display(head);
}
```

---

# 💻 C++ Implementation (DLL)

```cpp
#include <iostream>
using namespace std;

class Node {
public:
    int data;
    Node* prev;
    Node* next;

    Node(int val) {
        data = val;
        prev = next = NULL;
    }
};

void insert(Node*& head, int val) {
    Node* n = new Node(val);
    n->next = head;

    if (head)
        head->prev = n;

    head = n;
}

void display(Node* head) {
    while (head) {
        cout << head->data << " <-> ";
        head = head->next;
    }
    cout << "NULL";
}

int main() {
    Node* head = NULL;
    insert(head, 10);
    insert(head, 20);
    insert(head, 30);
    display(head);
}
```

---

# 💻 Java Implementation (DLL)

```java
class Node {
    int data;
    Node prev, next;

    Node(int d) {
        data = d;
        prev = next = null;
    }
}

public class DoublyLinkedList {
    Node head;

    void insert(int val) {
        Node n = new Node(val);
        n.next = head;

        if (head != null)
            head.prev = n;

        head = n;
    }

    void display() {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " <-> ");
            temp = temp.next;
        }
        System.out.println("NULL");
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.insert(10);
        dll.insert(20);
        dll.insert(30);
        dll.display();
    }
}
```

---

# 💻 Python Implementation (DLL)

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.prev = None
        self.next = None

class DoublyLinkedList:
    def __init__(self):
        self.head = None

    def insert(self, value):
        new = Node(value)
        new.next = self.head
        if self.head:
            self.head.prev = new
        self.head = new

    def display(self):
        temp = self.head
        while temp:
            print(temp.data, "<->", end=" ")
            temp = temp.next
        print("None")

dll = DoublyLinkedList()
dll.insert(10)
dll.insert(20)
dll.insert(30)
dll.display()
```

---

# 🎨 Doubly Linked List Visualization (Tkinter)

### Features

✔ Insert Node
✔ Visual prev ↔ next arrows
✔ Live update

---

## 💻 Tkinter Code (Python)

```python
import tkinter as tk

class DLLGUI:
    def __init__(self):
        self.root = tk.Tk()
        self.root.title("Doubly Linked List Visualization")

        self.nodes = []

        self.entry = tk.Entry(self.root)
        self.entry.pack()

        tk.Button(self.root, text="Insert",
                  command=self.insert).pack()

        self.canvas = tk.Canvas(self.root, width=900, height=250, bg="white")
        self.canvas.pack()

        self.root.mainloop()

    def insert(self):
        val = self.entry.get()
        if val:
            self.nodes.insert(0, val)
            self.draw()

    def draw(self):
        self.canvas.delete("all")
        x = 50
        for i, val in enumerate(self.nodes):
            self.canvas.create_rectangle(x, 100, x+70, 150)
            self.canvas.create_text(x+35, 125, text=val)

            if i > 0:
                self.canvas.create_line(x-30, 125, x, 125, arrow=tk.LAST)
                self.canvas.create_line(x, 135, x-30, 135, arrow=tk.LAST)

            x += 120

DLLGUI()
```

---

# 🧠 Important Interview Questions

✔ Difference between SLL & DLL
✔ Delete a node in O(1)
✔ Reverse DLL
✔ Convert DLL to Circular DLL

---

# 📝 Exam Notes (1–2 lines)

> Doubly Linked List allows **bidirectional traversal** using `prev` and `next` pointers, at the cost of extra memory.

---

## 🚀 Want Next?

✅ Circular Linked List
✅ Reverse DLL (step-by-step)
✅ CRUD Tkinter App
✅ Interview problems with solutions

Just tell me 😄
