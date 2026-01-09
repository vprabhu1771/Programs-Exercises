Below is a **complete, structured guide to AVL Trees** with **theory + implementations in C, C++, Java, Python**, and a **Tkinter GUI demo** for visualization.

---

# 🌳 AVL Tree (Adelson-Velsky and Landis Tree)

An **AVL Tree** is a **self-balancing Binary Search Tree (BST)** where:

> **Balance Factor = height(left subtree) − height(right subtree)**
> Allowed values: **−1, 0, +1**

If the balance factor goes outside this range, **rotations** are performed.

---

## 🔁 Rotations in AVL Tree

| Case | Condition   | Rotation       |
| ---- | ----------- | -------------- |
| LL   | Left-Left   | Right Rotation |
| RR   | Right-Right | Left Rotation  |
| LR   | Left-Right  | Left → Right   |
| RL   | Right-Left  | Right → Left   |

---

## ⏱️ Time Complexity

| Operation | Complexity |
| --------- | ---------- |
| Search    | O(log n)   |
| Insert    | O(log n)   |
| Delete    | O(log n)   |

---

# ✅ AVL TREE – C IMPLEMENTATION

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int key, height;
    struct Node *left, *right;
};

int height(struct Node *n) {
    return n ? n->height : 0;
}

int max(int a, int b) {
    return (a > b) ? a : b;
}

struct Node* newNode(int key) {
    struct Node* node = (struct Node*)malloc(sizeof(struct Node));
    node->key = key;
    node->left = node->right = NULL;
    node->height = 1;
    return node;
}

struct Node* rightRotate(struct Node* y) {
    struct Node* x = y->left;
    struct Node* T2 = x->right;

    x->right = y;
    y->left = T2;

    y->height = max(height(y->left), height(y->right)) + 1;
    x->height = max(height(x->left), height(x->right)) + 1;

    return x;
}

struct Node* leftRotate(struct Node* x) {
    struct Node* y = x->right;
    struct Node* T2 = y->left;

    y->left = x;
    x->right = T2;

    x->height = max(height(x->left), height(x->right)) + 1;
    y->height = max(height(y->left), height(y->right)) + 1;

    return y;
}

int getBalance(struct Node* n) {
    return n ? height(n->left) - height(n->right) : 0;
}

struct Node* insert(struct Node* node, int key) {
    if (!node) return newNode(key);

    if (key < node->key)
        node->left = insert(node->left, key);
    else if (key > node->key)
        node->right = insert(node->right, key);
    else
        return node;

    node->height = 1 + max(height(node->left), height(node->right));

    int balance = getBalance(node);

    if (balance > 1 && key < node->left->key)
        return rightRotate(node);

    if (balance < -1 && key > node->right->key)
        return leftRotate(node);

    if (balance > 1 && key > node->left->key) {
        node->left = leftRotate(node->left);
        return rightRotate(node);
    }

    if (balance < -1 && key < node->right->key) {
        node->right = rightRotate(node->right);
        return leftRotate(node);
    }

    return node;
}

void inorder(struct Node* root) {
    if (root) {
        inorder(root->left);
        printf("%d ", root->key);
        inorder(root->right);
    }
}

int main() {
    struct Node* root = NULL;
    root = insert(root, 10);
    root = insert(root, 20);
    root = insert(root, 30);
    root = insert(root, 40);

    inorder(root);
    return 0;
}
```

---

# ✅ AVL TREE – C++ IMPLEMENTATION

```cpp
#include <iostream>
using namespace std;

class Node {
public:
    int key, height;
    Node *left, *right;

    Node(int k) {
        key = k;
        height = 1;
        left = right = NULL;
    }
};

int height(Node* n) {
    return n ? n->height : 0;
}

int balance(Node* n) {
    return n ? height(n->left) - height(n->right) : 0;
}

Node* rightRotate(Node* y) {
    Node* x = y->left;
    Node* T2 = x->right;

    x->right = y;
    y->left = T2;

    y->height = max(height(y->left), height(y->right)) + 1;
    x->height = max(height(x->left), height(x->right)) + 1;

    return x;
}

Node* leftRotate(Node* x) {
    Node* y = x->right;
    Node* T2 = y->left;

    y->left = x;
    x->right = T2;

    x->height = max(height(x->left), height(x->right)) + 1;
    y->height = max(height(y->left), height(y->right)) + 1;

    return y;
}

Node* insert(Node* node, int key) {
    if (!node) return new Node(key);

    if (key < node->key)
        node->left = insert(node->left, key);
    else if (key > node->key)
        node->right = insert(node->right, key);
    else
        return node;

    node->height = max(height(node->left), height(node->right)) + 1;
    int b = balance(node);

    if (b > 1 && key < node->left->key)
        return rightRotate(node);

    if (b < -1 && key > node->right->key)
        return leftRotate(node);

    if (b > 1 && key > node->left->key) {
        node->left = leftRotate(node->left);
        return rightRotate(node);
    }

    if (b < -1 && key < node->right->key) {
        node->right = rightRotate(node->right);
        return leftRotate(node);
    }

    return node;
}

void inorder(Node* root) {
    if (root) {
        inorder(root->left);
        cout << root->key << " ";
        inorder(root->right);
    }
}

int main() {
    Node* root = NULL;
    root = insert(root, 10);
    root = insert(root, 20);
    root = insert(root, 30);
    inorder(root);
}
```

---

# ✅ AVL TREE – JAVA IMPLEMENTATION

```java
class AVLNode {
    int key, height;
    AVLNode left, right;

    AVLNode(int k) {
        key = k;
        height = 1;
    }
}

class AVLTree {

    int height(AVLNode n) {
        return n == null ? 0 : n.height;
    }

    int balance(AVLNode n) {
        return n == null ? 0 : height(n.left) - height(n.right);
    }

    AVLNode rightRotate(AVLNode y) {
        AVLNode x = y.left;
        AVLNode T2 = x.right;

        x.right = y;
        y.left = T2;

        y.height = Math.max(height(y.left), height(y.right)) + 1;
        x.height = Math.max(height(x.left), height(x.right)) + 1;

        return x;
    }

    AVLNode leftRotate(AVLNode x) {
        AVLNode y = x.right;
        AVLNode T2 = y.left;

        y.left = x;
        x.right = T2;

        x.height = Math.max(height(x.left), height(x.right)) + 1;
        y.height = Math.max(height(y.left), height(y.right)) + 1;

        return y;
    }

    AVLNode insert(AVLNode node, int key) {
        if (node == null)
            return new AVLNode(key);

        if (key < node.key)
            node.left = insert(node.left, key);
        else if (key > node.key)
            node.right = insert(node.right, key);
        else
            return node;

        node.height = Math.max(height(node.left), height(node.right)) + 1;

        int b = balance(node);

        if (b > 1 && key < node.left.key)
            return rightRotate(node);

        if (b < -1 && key > node.right.key)
            return leftRotate(node);

        if (b > 1 && key > node.left.key) {
            node.left = leftRotate(node.left);
            return rightRotate(node);
        }

        if (b < -1 && key < node.right.key) {
            node.right = rightRotate(node.right);
            return leftRotate(node);
        }

        return node;
    }

    void inorder(AVLNode root) {
        if (root != null) {
            inorder(root.left);
            System.out.print(root.key + " ");
            inorder(root.right);
        }
    }

    public static void main(String[] args) {
        AVLTree tree = new AVLTree();
        AVLNode root = null;

        root = tree.insert(root, 10);
        root = tree.insert(root, 20);
        root = tree.insert(root, 30);

        tree.inorder(root);
    }
}
```

---

# ✅ AVL TREE – PYTHON IMPLEMENTATION

```python
class Node:
    def __init__(self, key):
        self.key = key
        self.left = None
        self.right = None
        self.height = 1

def height(n):
    return n.height if n else 0

def balance(n):
    return height(n.left) - height(n.right) if n else 0

def right_rotate(y):
    x = y.left
    T2 = x.right

    x.right = y
    y.left = T2

    y.height = max(height(y.left), height(y.right)) + 1
    x.height = max(height(x.left), height(x.right)) + 1

    return x

def left_rotate(x):
    y = x.right
    T2 = y.left

    y.left = x
    x.right = T2

    x.height = max(height(x.left), height(x.right)) + 1
    y.height = max(height(y.left), height(y.right)) + 1

    return y

def insert(node, key):
    if not node:
        return Node(key)

    if key < node.key:
        node.left = insert(node.left, key)
    elif key > node.key:
        node.right = insert(node.right, key)
    else:
        return node

    node.height = max(height(node.left), height(node.right)) + 1
    b = balance(node)

    if b > 1 and key < node.left.key:
        return right_rotate(node)
    if b < -1 and key > node.right.key:
        return left_rotate(node)
    if b > 1 and key > node.left.key:
        node.left = left_rotate(node.left)
        return right_rotate(node)
    if b < -1 and key < node.right.key:
        node.right = right_rotate(node.right)
        return left_rotate(node)

    return node
```

---

# 🖥️ AVL TREE VISUALIZATION – PYTHON Tkinter

```python
import tkinter as tk

class AVLVisualizer:
    def __init__(self, root):
        self.root = root
        self.tree = None

        self.canvas = tk.Canvas(root, width=800, height=400, bg="white")
        self.canvas.pack()

        self.entry = tk.Entry(root)
        self.entry.pack()

        tk.Button(root, text="Insert", command=self.insert).pack()

    def insert(self):
        val = int(self.entry.get())
        self.tree = insert(self.tree, val)
        self.draw()

    def draw(self):
        self.canvas.delete("all")
        self._draw(self.tree, 400, 40, 150)

    def _draw(self, node, x, y, dx):
        if node:
            self.canvas.create_oval(x-15, y-15, x+15, y+15, fill="lightblue")
            self.canvas.create_text(x, y, text=str(node.key))

            if node.left:
                self.canvas.create_line(x, y, x-dx, y+60)
                self._draw(node.left, x-dx, y+60, dx//2)

            if node.right:
                self.canvas.create_line(x, y, x+dx, y+60)
                self._draw(node.right, x+dx, y+60, dx//2)

root = tk.Tk()
root.title("AVL Tree Visualizer")
AVLVisualizer(root)
root.mainloop()
```

---

## 🎯 Want next?

* AVL **Delete operation**
* **Animated rotations**
* **Comparison: BST vs AVL vs Red-Black Tree**
* **Exam-ready notes & diagrams**
* **PDF / PPT version**

Just tell me 👍
