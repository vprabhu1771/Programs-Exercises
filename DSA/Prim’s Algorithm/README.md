#  Prim's Algorithm in Tamil | Data Structures and Algorithms in Tamil | CD3291 Lectures in Tamil 

```
https://www.youtube.com/watch?v=NgJfXx7yPyU
```

```
https://www.geeksforgeeks.org/dsa/prims-minimum-spanning-tree-mst-greedy-algo-5/
```

Below is a **complete DSA guide for Prim’s Algorithm** with:

✅ Concept & steps
✅ Time complexity
✅ **C, C++, Java, Python implementations**
✅ **Tkinter GUI (Python) – visual + table output**

---

# 🌳 Prim’s Algorithm (Minimum Spanning Tree)

**Prim’s Algorithm** finds a **Minimum Spanning Tree (MST)** for a **connected, weighted, undirected graph**.

> MST = connects all vertices with **minimum total edge weight** and **no cycles**.

---

## 🧠 Core Idea

1. Start from any vertex
2. Grow the MST by repeatedly adding the **minimum weight edge**
3. The edge must connect:

   * a **visited** vertex
   * to an **unvisited** vertex
4. Stop when all vertices are included

---

## ⏱️ Time Complexity

| Data Structure        | Complexity     |
| --------------------- | -------------- |
| Adjacency Matrix      | **O(V²)**      |
| Priority Queue (Heap) | **O(E log V)** |

---

## 🔢 Example Graph

```
   (2)
0 ------ 1
| \      |
6  8     5
|    \   |
2 ------ 3
    (7)
```

---

# 🧩 C Implementation (Adjacency Matrix)

```c
#include <stdio.h>
#include <limits.h>

#define V 5

int minKey(int key[], int mstSet[]) {
    int min = INT_MAX, min_index;
    for (int v = 0; v < V; v++)
        if (!mstSet[v] && key[v] < min)
            min = key[v], min_index = v;
    return min_index;
}

void primMST(int graph[V][V]) {
    int parent[V], key[V], mstSet[V];

    for (int i = 0; i < V; i++)
        key[i] = INT_MAX, mstSet[i] = 0;

    key[0] = 0;
    parent[0] = -1;

    for (int count = 0; count < V - 1; count++) {
        int u = minKey(key, mstSet);
        mstSet[u] = 1;

        for (int v = 0; v < V; v++)
            if (graph[u][v] && !mstSet[v] && graph[u][v] < key[v]) {
                parent[v] = u;
                key[v] = graph[u][v];
            }
    }

    printf("Edge   Weight\n");
    for (int i = 1; i < V; i++)
        printf("%d - %d    %d\n", parent[i], i, graph[i][parent[i]]);
}
```

---

# 🧩 C++ Implementation (Priority Queue)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    int V = 5;
    vector<vector<pair<int,int>>> adj(V);

    adj[0].push_back({1,2});
    adj[1].push_back({0,2});
    adj[0].push_back({3,6});
    adj[3].push_back({0,6});

    priority_queue<pair<int,int>, vector<pair<int,int>>, greater<>> pq;
    vector<int> key(V, INT_MAX), parent(V, -1);
    vector<bool> inMST(V, false);

    pq.push({0, 0});
    key[0] = 0;

    while (!pq.empty()) {
        int u = pq.top().second;
        pq.pop();
        inMST[u] = true;

        for (auto [v, weight] : adj[u]) {
            if (!inMST[v] && weight < key[v]) {
                key[v] = weight;
                pq.push({key[v], v});
                parent[v] = u;
            }
        }
    }

    for (int i = 1; i < V; i++)
        cout << parent[i] << " - " << i << endl;
}
```

---

# 🧩 Java Implementation

```java
import java.util.*;

class Prim {
    static final int V = 5;

    int minKey(int key[], Boolean mstSet[]) {
        int min = Integer.MAX_VALUE, minIndex = -1;
        for (int v = 0; v < V; v++)
            if (!mstSet[v] && key[v] < min) {
                min = key[v];
                minIndex = v;
            }
        return minIndex;
    }

    void primMST(int graph[][]) {
        int parent[] = new int[V];
        int key[] = new int[V];
        Boolean mstSet[] = new Boolean[V];

        Arrays.fill(key, Integer.MAX_VALUE);
        Arrays.fill(mstSet, false);

        key[0] = 0;
        parent[0] = -1;

        for (int count = 0; count < V - 1; count++) {
            int u = minKey(key, mstSet);
            mstSet[u] = true;

            for (int v = 0; v < V; v++)
                if (graph[u][v] != 0 && !mstSet[v] && graph[u][v] < key[v]) {
                    parent[v] = u;
                    key[v] = graph[u][v];
                }
        }

        for (int i = 1; i < V; i++)
            System.out.println(parent[i] + " - " + i);
    }
}
```

---

# 🧩 Python Implementation

```python
import heapq

def prim(graph):
    V = len(graph)
    visited = [False]*V
    pq = [(0, 0)]
    total = 0

    while pq:
        weight, u = heapq.heappop(pq)
        if visited[u]:
            continue
        visited[u] = True
        total += weight

        for v, w in graph[u]:
            if not visited[v]:
                heapq.heappush(pq, (w, v))

    return total
```

---

# 🖼️ Tkinter GUI – Prim’s Algorithm

### Features

✅ Step-by-step edge selection
✅ MST table output
✅ Total cost display

```python
import tkinter as tk
import heapq

graph = {
    0: [(1, 2), (3, 6)],
    1: [(0, 2), (2, 3)],
    2: [(1, 3), (3, 7)],
    3: [(0, 6), (2, 7)]
}

def run_prim():
    visited = set()
    pq = [(0, 0, -1)]
    result.delete(1.0, tk.END)
    total = 0

    while pq:
        w, u, p = heapq.heappop(pq)
        if u in visited:
            continue
        visited.add(u)
        total += w
        if p != -1:
            result.insert(tk.END, f"{p} - {u} : {w}\n")

        for v, wt in graph[u]:
            if v not in visited:
                heapq.heappush(pq, (wt, v, u))

    result.insert(tk.END, f"\nTotal Cost: {total}")

root = tk.Tk()
root.title("Prim's Algorithm")

tk.Button(root, text="Run Prim's Algorithm", command=run_prim).pack()
result = tk.Text(root, height=12, width=40)
result.pack()

root.mainloop()
```

---

## 🎯 Want More?

I can also give you:

✔ Step-by-step **table trace**
✔ **Animated Tkinter graph visualization**
✔ **Comparison with Kruskal**
✔ **Interview Q&A + MCQs**
✔ **Exam-ready notes PDF**

Just tell me 👍
