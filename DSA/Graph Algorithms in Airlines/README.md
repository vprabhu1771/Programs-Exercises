Below is **a clear mini-project style explanation + code samples in C, C++, Java, Python, and Python Tkinter** showing how **graph algorithms (Minimum Spanning Tree – Prim/Kruskal)** can be used in **airline route cost optimization**
→ specifically **finding the total minimum cost** needed to connect all airports.

---

# ✈️ **Application of Graph Algorithms in Airline Transportation**

### **Problem Scenario**

Airline companies maintain a network of flights between airports.
Each **airport = node**, each **flight route = edge**, and **ticket/fuel/maintenance cost = edge weight**.

> Using **Minimum Spanning Tree (MST)** (Prim’s or Kruskal’s algorithm), we can compute the **minimum total operational cost** required to connect all airports **while avoiding extra routes**.

### **Why MST?**

| Airline Goal             | Graph Concept               |
| ------------------------ | --------------------------- |
| Reduce operational costs | minimize total edge weights |
| Connect all airports     | spanning tree               |
| Avoid redundant routes   | no cycles in MST            |

---

# 📌 **Example Graph (Airports & Costs)**

| Route | Cost |
| ----- | ---- |
| A – B | 4    |
| A – C | 3    |
| B – C | 1    |
| B – D | 2    |
| C – D | 4    |
| C – E | 2    |
| D – E | 3    |

✔ Minimum Cost MST = **1 + 2 + 2 + 3 = 8**

---

# 🧮 **OUTPUT WE EXPECT**

```
Total minimum cost to connect all airports = 8
```

---

---

# 🧑‍💻 **C Program (Kruskal’s Algorithm – MST Cost)**

```c
#include <stdio.h>

struct Edge {
    int u, v, w;
};

int parent[100];

int find(int x) {
    if(parent[x] == x) return x;
    return parent[x] = find(parent[x]);
}

void unionSet(int x, int y) {
    parent[find(x)] = find(y);
}

int main() {
    struct Edge edges[] = {{1,2,4},{1,3,3},{2,3,1},{2,4,2},{3,4,4},{3,5,2},{4,5,3}};
    int n = 5, m = 7;

    for(int i=1;i<=n;i++) parent[i]=i;

    // sort by weight
    for(int i=0;i<m;i++)
        for(int j=i+1;j<m;j++)
            if(edges[i].w > edges[j].w){
                struct Edge temp=edges[i]; edges[i]=edges[j]; edges[j]=temp;
            }

    int total=0;
    for(int i=0;i<m;i++){
        if(find(edges[i].u) != find(edges[i].v)){
            total += edges[i].w;
            unionSet(edges[i].u, edges[i].v);
        }
    }

    printf("Total minimum cost = %d\n", total);
    return 0;
}
```

---

# 🧑‍💻 **C++ Program (Prim’s Algorithm – MST Cost)**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main(){
    int n=5;
    vector<vector<pair<int,int>>> g(n+1);
    g[1]={{2,4},{3,3}};
    g[2]={{1,4},{3,1},{4,2}};
    g[3]={{1,3},{2,1},{4,4},{5,2}};
    g[4]={{2,2},{3,4},{5,3}};
    g[5]={{3,2},{4,3}};

    vector<int> dist(n+1,1e9), vis(n+1,0);
    priority_queue<pair<int,int>,vector<pair<int,int>>,
                    greater<pair<int,int>>> pq;
    
    dist[1]=0;
    pq.push({0,1});
    int total=0;

    while(!pq.empty()){
        auto [d,u]=pq.top(); pq.pop();
        if(vis[u]) continue;
        vis[u]=1;
        total+=d;
        for(auto [v,w]:g[u])
            if(!vis[v] && w < dist[v]){
                dist[v]=w;
                pq.push({w,v});
            }
    }
    cout<<"Total minimum cost = "<<total<<endl;
}
```

---

# 🧑‍💻 **Java Program (Kruskal – MST Cost)**

```java
import java.util.*;

class Edge implements Comparable<Edge>{
    int u,v,w;
    Edge(int u,int v,int w){this.u=u;this.v=v;this.w=w;}
    public int compareTo(Edge e){ return this.w-e.w; }
}

public class AirlineMST {
    static int[] parent = new int[100];

    static int find(int x){
        if(parent[x]==x) return x;
        return parent[x]=find(parent[x]);
    }

    static void unionSet(int a,int b){
        parent[find(a)] = find(b);
    }

    public static void main(String[] args){
        List<Edge> edges = Arrays.asList(
            new Edge(1,2,4), new Edge(1,3,3), new Edge(2,3,1),
            new Edge(2,4,2), new Edge(3,4,4), new Edge(3,5,2),
            new Edge(4,5,3)
        );

        for(int i=1;i<=5;i++) parent[i]=i;

        Collections.sort(edges);
        int cost=0;

        for(Edge e:edges){
            if(find(e.u)!=find(e.v)){
                cost+=e.w;
                unionSet(e.u,e.v);
            }
        }
        System.out.println("Total minimum cost = "+cost);
    }
}
```

---

# 🐍 **Python Program (Prim’s Algorithm – MST Cost)**

```python
import heapq

graph = {
    1:[(2,4),(3,3)],
    2:[(1,4),(3,1),(4,2)],
    3:[(1,3),(2,1),(4,4),(5,2)],
    4:[(2,2),(3,4),(5,3)],
    5:[(3,2),(4,3)]
}

visited=set()
pq=[(0,1)]
total_cost=0

while pq:
    cost, node = heapq.heappop(pq)
    if node in visited: continue
    visited.add(node)
    total_cost += cost
    
    for v,w in graph[node]:
        if v not in visited:
            heapq.heappush(pq,(w,v))

print("Total minimum cost =", total_cost)
```

---

# 🐍🎛 **Python Tkinter GUI – Display MST Cost**

> Minimal GUI to **input graph edges and show MST cost**

```python
import tkinter as tk
from tkinter import messagebox
import heapq

def mst_cost():
    # fixed sample graph
    graph = {
        1:[(2,4),(3,3)],
        2:[(1,4),(3,1),(4,2)],
        3:[(1,3),(2,1),(4,4),(5,2)],
        4:[(2,2),(3,4),(5,3)],
        5:[(3,2),(4,3)]
    }
    visited=set()
    pq=[(0,1)]
    total=0

    while pq:
        cost,node = heapq.heappop(pq)
        if node in visited: continue
        visited.add(node)
        total += cost
        for v,w in graph[node]:
            if v not in visited:
                heapq.heappush(pq,(w,v))

    messagebox.showinfo("MST Result",
        f"Total minimum airline route cost = {total}")

root = tk.Tk()
root.title("Airline Route Optimization")
tk.Button(root, text="Compute Minimum Cost (MST)",
          command=mst_cost, font=("Arial",14)).pack(pady=30)

root.mainloop()
```

---

## 🎯 **Final Result**

> **Total minimum cost to connect all airports = 8**

You can now:
✔ use this as a **college mini project**
✔ extend with **map visualization, airport icons, route editor, database**
✔ build GUI comparison **Prim vs Kruskal vs Dijkstra**

---

# 🔧 Want to convert into:

* PDF report
* PowerPoint project presentation
* Tkinter visualization with airline map
* Flutter frontend, Django/Laravel backend

Just tell me — I’ll generate the next step!
