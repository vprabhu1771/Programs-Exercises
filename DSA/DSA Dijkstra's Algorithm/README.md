Below is a **complete DSA explanation of Dijkstra’s Algorithm** with
✔ **Step-by-step working**
✔ **C program**
✔ **C++ program**
✔ **Java program**
✔ **Python program**
✔ **Python Tkinter GUI visualization**

---

## 🔹 What is Dijkstra’s Algorithm?

Dijkstra’s Algorithm finds the **shortest path from a single source vertex** to **all other vertices** in a **weighted graph** (weights must be **non-negative**).

---

## 🔹 Where it is used

* GPS & Maps 🗺️
* Network routing
* Shortest path in graphs
* Logistics & transport systems

---

## 🔹 Algorithm Steps

1. Initialize distance of source = `0`
2. Set all other distances = `∞`
3. Mark all vertices as **unvisited**
4. Pick the **unvisited vertex with minimum distance**
5. Update distances of its adjacent vertices
6. Mark the vertex as **visited**
7. Repeat until all vertices are visited

---

## 🔹 Example Graph

```
     (0)
   2 / \ 4
    /   \
  (1)--3--(2)
      1
```

Source = `0`

---

# ✅ C Program – Dijkstra’s Algorithm

```c
#include <stdio.h>
#define V 5
#define INF 99999

int minDistance(int dist[], int visited[]) {
    int min = INF, index;
    for (int i = 0; i < V; i++)
        if (!visited[i] && dist[i] <= min) {
            min = dist[i];
            index = i;
        }
    return index;
}

void dijkstra(int graph[V][V], int src) {
    int dist[V], visited[V];

    for (int i = 0; i < V; i++) {
        dist[i] = INF;
        visited[i] = 0;
    }

    dist[src] = 0;

    for (int i = 0; i < V - 1; i++) {
        int u = minDistance(dist, visited);
        visited[u] = 1;

        for (int v = 0; v < V; v++)
            if (!visited[v] && graph[u][v] &&
                dist[u] != INF &&
                dist[u] + graph[u][v] < dist[v])
                dist[v] = dist[u] + graph[u][v];
    }

    printf("Vertex \t Distance from Source\n");
    for (int i = 0; i < V; i++)
        printf("%d \t %d\n", i, dist[i]);
}

int main() {
    int graph[V][V] = {
        {0, 10, 0, 0, 5},
        {10, 0, 1, 0, 2},
        {0, 1, 0, 4, 0},
        {0, 0, 4, 0, 3},
        {5, 2, 0, 3, 0}
    };

    dijkstra(graph, 0);
    return 0;
}
```

---

# ✅ C++ Program

```cpp
#include <iostream>
using namespace std;

#define V 5
#define INF 99999

int minDistance(int dist[], bool visited[]) {
    int min = INF, index;
    for (int i = 0; i < V; i++)
        if (!visited[i] && dist[i] <= min) {
            min = dist[i];
            index = i;
        }
    return index;
}

void dijkstra(int graph[V][V], int src) {
    int dist[V];
    bool visited[V];

    for (int i = 0; i < V; i++) {
        dist[i] = INF;
        visited[i] = false;
    }

    dist[src] = 0;

    for (int i = 0; i < V - 1; i++) {
        int u = minDistance(dist, visited);
        visited[u] = true;

        for (int v = 0; v < V; v++)
            if (!visited[v] && graph[u][v] &&
                dist[u] + graph[u][v] < dist[v])
                dist[v] = dist[u] + graph[u][v];
    }

    cout << "Vertex Distance\n";
    for (int i = 0; i < V; i++)
        cout << i << " \t " << dist[i] << endl;
}

int main() {
    int graph[V][V] = {
        {0, 10, 0, 0, 5},
        {10, 0, 1, 0, 2},
        {0, 1, 0, 4, 0},
        {0, 0, 4, 0, 3},
        {5, 2, 0, 3, 0}
    };

    dijkstra(graph, 0);
    return 0;
}
```

---

# ✅ Java Program

```java
class Dijkstra {
    static final int V = 5;
    static final int INF = 99999;

    int minDistance(int dist[], boolean visited[]) {
        int min = INF, index = -1;
        for (int i = 0; i < V; i++)
            if (!visited[i] && dist[i] <= min) {
                min = dist[i];
                index = i;
            }
        return index;
    }

    void dijkstra(int graph[][], int src) {
        int dist[] = new int[V];
        boolean visited[] = new boolean[V];

        for (int i = 0; i < V; i++) {
            dist[i] = INF;
            visited[i] = false;
        }

        dist[src] = 0;

        for (int i = 0; i < V - 1; i++) {
            int u = minDistance(dist, visited);
            visited[u] = true;

            for (int v = 0; v < V; v++)
                if (!visited[v] && graph[u][v] != 0 &&
                    dist[u] + graph[u][v] < dist[v])
                    dist[v] = dist[u] + graph[u][v];
        }

        System.out.println("Vertex Distance");
        for (int i = 0; i < V; i++)
            System.out.println(i + " \t " + dist[i]);
    }

    public static void main(String[] args) {
        int graph[][] = {
            {0, 10, 0, 0, 5},
            {10, 0, 1, 0, 2},
            {0, 1, 0, 4, 0},
            {0, 0, 4, 0, 3},
            {5, 2, 0, 3, 0}
        };

        new Dijkstra().dijkstra(graph, 0);
    }
}
```

---

# ✅ Python Program

```python
import sys

INF = sys.maxsize
V = 5

def min_distance(dist, visited):
    min_val = INF
    index = -1
    for i in range(V):
        if not visited[i] and dist[i] < min_val:
            min_val = dist[i]
            index = i
    return index

def dijkstra(graph, src):
    dist = [INF] * V
    visited = [False] * V
    dist[src] = 0

    for _ in range(V - 1):
        u = min_distance(dist, visited)
        visited[u] = True

        for v in range(V):
            if graph[u][v] > 0 and not visited[v] and \
               dist[u] + graph[u][v] < dist[v]:
                dist[v] = dist[u] + graph[u][v]

    for i in range(V):
        print(f"{i} -> {dist[i]}")

graph = [
    [0,10,0,0,5],
    [10,0,1,0,2],
    [0,1,0,4,0],
    [0,0,4,0,3],
    [5,2,0,3,0]
]

dijkstra(graph, 0)
```

---

# ✅ Python Tkinter GUI – Dijkstra Visualization

```python
import tkinter as tk
import sys

INF = sys.maxsize

graph = [
    [0,10,0,0,5],
    [10,0,1,0,2],
    [0,1,0,4,0],
    [0,0,4,0,3],
    [5,2,0,3,0]
]

def dijkstra():
    dist = [INF]*5
    visited = [False]*5
    dist[0] = 0

    for _ in range(4):
        u = min((d for d in range(5) if not visited[d]),
                key=lambda x: dist[x])
        visited[u] = True

        for v in range(5):
            if graph[u][v] and not visited[v]:
                dist[v] = min(dist[v], dist[u] + graph[u][v])

    result.delete(1.0, tk.END)
    for i in range(5):
        result.insert(tk.END, f"Node {i} : {dist[i]}\n")

root = tk.Tk()
root.title("Dijkstra Algorithm")

tk.Button(root, text="Run Dijkstra", command=dijkstra).pack()
result = tk.Text(root, height=10, width=30)
result.pack()

root.mainloop()
```

---

## 🔹 Time Complexity

| Implementation | Complexity     |
| -------------- | -------------- |
| Array Based    | **O(V²)**      |
| Min Heap       | **O(E log V)** |

---

If you want next:
✔ **Step-by-step table output**
✔ **Priority Queue version**
✔ **Animated Tkinter graph UI**

Just tell 👍
