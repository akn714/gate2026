
```c
for (int i=2;i<=n;i*2) {}
// complexity => O(logn)
```

##### complexity of sorting a sorted array
- Insertion sort: O(n) -> best when array is already sorted
- selection sort: O(n^2)
- merge sort: O(n * log(n))
- Quick sort: O(n^2), normally O(n * log(n))
---
#### Algorithms
- Minimum Spanning Tree (MST)
	- Prim's Algorithm
	- Kruskal’s Algorithm (one by one highlight lighest edge)
- shortest path
	- Floyd–Warshall Algorithm: All-pairs shortest paths
	- Dijkstra’s Algorithm: Single-source shortest path
	- Bellman–Ford Algorithm: Single-source shortest path (with negative weights)
---
#### Optimal merge tree
<img src="../BIN/Pasted image 20260206230314.png">

- Total record movements = sum of internal nodes = 44 + 94 + 65 + 159 = 362
- Worst case no. of comparisons made while merging = sum of (m+n-1) for each
									       = (44-1) + (94-1) + (65-1) + (159-1) = 358
- (m+n-1) => no. of comparisons for 2 sorted array 

---

**perfect binary tree**
- all levels are fills completely

**complete binary tree**
- fill children from left

**strict binary tree / full binary tree**
- every node has 2 or 0 children
- should be complete already

**max / min heap**
- complete binary tree

##### Minimum spanning tree
- minimum spanning tree is unique for a given tree
- MST doesn't make cycle

---
### 0/1 Knapsack problem

**Dynamic approach**
<img src="../BIN/Pasted image 20260207160854.png">

**Greedy approach** -> take value by weight ratio
