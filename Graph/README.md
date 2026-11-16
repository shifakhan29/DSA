# Graph Notes - Organized

This folder contains today's graph theory study notes, organized by topic and problem pattern.

## Study Roadmap

1. Graph Fundamentals
2. Cycle Detection
3. Bipartite Graphs
4. Disjoint Set Union (DSU)
5. Topological Sort
6. Dijkstra's Algorithm
7. LeetCode Graph Problems

## 1) Graph Fundamentals

Notebook: `01_graph_fundamentals/graph_fundamentals.ipynb`

Key concepts:
- Graph = vertices + edges
- Directed vs undirected graphs
- Weighted vs unweighted graphs
- Degree, path, cycle, connected components
- Adjacency list, adjacency matrix, edge list
- BFS and DFS traversal

Important idea:
- Use adjacency list for most graph problems.
- BFS is best for shortest path in unweighted graphs.
- DFS is useful for connectivity, cycle, and component detection.

Complexity:
- Traversal: O(V + E)
- Extra space: O(V)

---

## 2) Cycle Detection

Notebook: `02_cycle_detection/cycle_detection.ipynb`

Topics covered:
- Undirected graph cycle detection using DFS
- Undirected graph cycle detection using BFS
- Directed graph cycle detection using DFS
- Directed graph cycle detection using Kahn's algorithm (BFS / indegree)

Key idea:
- In undirected graphs, a back edge to a visited parent indicates a cycle.
- In directed graphs, a cycle exists if DFS revisits a node on the current recursion stack.
- Kahn's algorithm detects cycles when the count of processed nodes is less than V.

Typical use:
- Detecting invalid dependencies
- Topological sort validation
- Detecting loops in networks

---

## 3) Bipartite Graphs

Notebook: `03_bipartite_graph/bipartite_check.ipynb`

Key concepts:
- A graph is bipartite if vertices can be colored with 2 colors such that no edge connects same-colored nodes.
- BFS/DFS coloring property
- Alternate color assignment in connected components

Main condition:
- If a node is revisited with the same color, the graph is not bipartite.

Use cases:
- Graph coloring problems
- Resource assignment problems
- Matching and scheduling tasks

---

## 4) Disjoint Set Union (DSU)

Notebook: `04_disjoint_set_union/dsu_basics.ipynb`

Key concepts:
- Union-Find / DSU tracks connected components efficiently.
- `find(x)` returns parent/root
- `union(a, b)` merges two sets
- Path compression reduces tree height
- Union by rank/size keeps structure balanced

Common applications:
- Cycle detection in undirected graphs
- Connectivity and component counting
- Network connectivity problems
- Kruskal's MST

Complexity:
- Almost constant amortized time per operation
- Very efficient for large graphs

---

## 5) Topological Sorting

Notebook: `05_topological_sorting/topological_sort.ipynb`

Key concepts:
- Valid ordering of vertices in a DAG
- For every edge u -> v, u appears before v
- DFS with stack
- Kahn's Algorithm (BFS + indegree)

Important points:
- Topological sort exists only for DAGs
- If the produced order contains fewer than V nodes, the graph has a cycle

Applications:
- Course scheduling
- Dependency resolution
- Build systems
- Task ordering

---

## 6) Dijkstra's Algorithm

Notebooks:
- `06_Dijksta's_algorithm/dijkstra.ipynb`
- `06_Dijksta's_algorithm/shortest_path.ipynb`

Key concepts:
- Shortest path in weighted graphs with non-negative edges
- Priority queue / min-heap optimization
- Greedy choice: choose the currently smallest distance node
- Relax edges until the shortest distances are finalized

Main idea:
- Each vertex stores the minimum cost found so far.
- Repeatedly pick the nearest unvisited node and relax its neighbors.

Applications:
- Network routing
- Distance maps
- GPS and traffic shortest path

Complexity:
- With priority queue: O((V + E) log V)

---

## 7) LeetCode Graph Practice

Notebook: `Graph_leetcode/leetcode_solutions.ipynb`

Topics covered:
- Number of Provinces
- Course Schedule I / II
- Cycle detection problems
- DSU-based connectivity problems
- Satisfiability of Equality Equations
- Number of Operations to Make Network Connected
- Count Unreachable Pairs of Nodes
- Network Delay Time
- Shortest Path in Binary Matrix
- Path with Minimum Effort (LeetCode 1631)

Pattern reminder:
- Connected components -> DFS/BFS or DSU
- Topological order -> Kahn or DFS
- Shortest path -> BFS for unweighted, Dijkstra for weighted edges
- Cycle detection -> visited-state logic or DSU

### Special note: LeetCode 1631 — Path with Minimum Effort

This one is a classic minimum-cost path problem on a grid. The idea is:
- Each move from one cell to a neighbor has a cost equal to the absolute height difference.
- The path cost is the maximum edge cost along that path.
- We need the minimum possible maximum difference along the route from start to end.

This is solved efficiently with a priority queue and a Dijkstra-style relaxation:
- Keep the best known "effort" to reach each cell.
- Pop the cell with the smallest current effort.
- Relax its neighbors by taking the maximum of the current effort and the new step cost.
- Stop when the destination is reached.

Pattern:
- Weighted shortest path on a graph-like grid
- Use priority queue / min-heap
- Time complexity: O((V + E) log V) in graph terms, which for a grid becomes O(R*C log(R*C))

---

## Quick Revision Checklist

Before a graph interview or coding test, revise these:

- [ ] Difference between directed and undirected graphs
- [ ] BFS vs DFS trade-offs
- [ ] How to represent graphs
- [ ] Detecting cycles
- [ ] Bipartite check using coloring
- [ ] DSU operations: find + union
- [ ] Topological sort logic
- [ ] Dijkstra's shortest path with priority queue
- [ ] When to use DFS, BFS, DSU, or greedy shortest path

## Best Order to Study

1. Graph Fundamentals
2. Cycle Detection
3. Bipartite Graphs
4. DSU
5. Topological Sort
6. Dijkstra's Algorithm
7. Practice LeetCode graph questions

## Final Reminder

Graph problems usually become easy once you identify the correct pattern:
- BFS for shortest paths in unweighted graphs
- DFS for connectivity and cycle detection
- Topological sort for DAG ordering
- DSU for connectivity and union problems
- Dijkstra for shortest paths with non-negative weights

This is a clean beginner-friendly graph study set for revision and practice.
