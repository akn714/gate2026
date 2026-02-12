
#### Uninformed search
- BFS
	- queue
	- **completeness**: BFS always finds a solution if it exists.
	- finds optimal path for unweighted graphs
	- time complexity:
		- for graph: **O(V+E)** (V - no. of vertices/nodes, E - no. of edges in graph)
		- or **O(b^d)**, d -> depth, b -> branching factor
		- for tree: **O(V)**, as E = V - 1 in tree, (V -> verties/nodes)
> Branching factor is the number of children (successors) each node has in a tree or graph data structure, representing the breadth of a search space.
- DFS
	- stack
	- **completeness**: DFS does not guarantee a solution if one exists, especially in infinite search space. DFS is non optimal and incomplete.
	- time complexity: **O(b^d)** (b -> branch factor, d -> depth)
	- space complexity: **O(bxd)**
	- Depth-First Search (DFS) is considered incomplete because it can get stuck exploring an infinitely deep path or a cycle in the graph, preventing it from ever finding a solution that might exist on another branch.
- DLS (Depth Limited Search)
	- Simple DFS for but for limited depth
	- **completeness**: Incomplete, not optimal
	- time complexity: **O(b^L)** (b -> branch factor, L -> depth limit)
	- space complexity: **O(bxL)**
- IDS (Iterative Deepening Search) or IDDFS (Iterative Deepening Depth First Search)
	- combines advantages of DFS and BFS
	- **completeness**: it is completed and optimal
	- time complexity: **O(b^d)**
	- space complexity: **O(bxd)**
	- Iteratively increasing depth of the graph/tree and applying DFS (simply DLS but for multiple depths)
	- It's solution is same as BFS
- Uniform cost search (UCS)
	- Used for weighted graph
	- Simply BFS with priority queue, priority based on path cost of node from start node.
	- If weights of all edges is equal then solution of UCS = BFS
	- Variant of Dijkstra's Algorithm
	- It is less efficient with large graphs due to memory and time
	- It doesn't work on negative (-ve) edges
	- **completeness**: complete and optimal
	<img src="./BIN/Pasted image 20260211190234.png">
	<img src="./BIN/Pasted image 20260211184116.png">

#### Informed search
**Heuristic Function: h(n):**
- It is a function that estimates the cost of the cheapest path from a node n to the goal.
- The quality of the heuristic greatly influences the efficiency of the search.
- A good heuristic should be **admissible and consistent/monotonic**
```
Admissible means that heuristics of any node does not over estimate the cost of path from node to goal node.
h(n) <= cost of node to goal node

Consistent means heuristics should satisfy below:
h(n) <= h(n*) + C(n-n*)

h(n*) -> heuristics of neighbor node
C(n-n*) -> cost of node to neighbor node

======
TRUE: If Consistent then Admissible
FALSE: If Admissible then consistent
======
```


- Greedy Best First Search
	- select the node with lowest heuristic value (ignore edge weight)
	- **completeness:** Incomplete and not optimal
	- It doesn't consider the cost to reach a node (i.e. weight or edges)
	- **Advantage**: Faster than uninformed search algorithms when the heuristic is good.
	- **Disadvantage**: Can lead to suboptimal paths as it ignores the actual cost to reach nodes.
	- time complexity: **O(b^d)**
	- space complexity: **O(b^d)**
	<img src="./BIN/Pasted image 20260211190525.png">

- A* Search Algorithm
	- select the node with lowest value of function.
	- `function` f(n) = h(n) + cost (start node to particular node)
	- time and space complexity: **O(B^D)**
	- optimality: depends on goodness of heuristics 
	- **completeness**: completed
	- A* should have admissible heuristics (but not mandatory to be consistent heuristics)
- Weighted A* (WA*) Algorithm
	- `f(n) = g(n) + w * h(n)`
	- g(n) -> path cost
	- w -> weight
	- h(n) -> heuristics of the node
	- time complexity: **O(b^d)**
	```
	If w is large, then WA* becomes GBFS
	If w = 1, then WA* becomes A*
	```

- Iterative Deepening A* algorithm (IDA*)
	- Iteration 1: Threshold value = `f` value of start node
		- start A* on graph
		- now, if node `f` value > threshold value then those nodes are pruned and not visited.
		- now threshold = min `f` value of the pruned node
	- Iteration 2: with 2nd threshold value
	- and so on...
	- time complexity: **O(b^d)**
	- saves space complexity of A*
	- space complexity: **O(bxd)**
>The **open list** is a collection of all the nodes that have been discovered by the algorithm but have not yet been fully evaluated or expanded.


- Adversarial Search
	- users backtracking and DFS
	- 2 player games, both play optimally
	- zero sum game => if one win then other loose
	- time and space complexity: **O(b^d)** and **O(bxd)**
	- **completeness**: complete and optimal
	- MinMax algo:
		- player 1: minimize result / cost
		- player 2: maximize result / cost
		<img src="./BIN/Pasted image 20260211234950.png">
	- Alpha-Beta Pruning
		- alpha -> max
		- beta -> min
		<img src="./BIN/Pasted image 20260212001131.png">

---
#### Proposition Logic

- conjunction -> AND
- disjunction -> OR
- implication -> A -> B
	- if both are same then A -> B is true
	- if both are different then A -> B is same as B
- biconditional (equivalence): A <-> B
	- True if both same
	- False if both are different

```
Tautology -> always True
Contradiction -> always False
Contingency -> True and False both
Satisfiable -> at least one time True
```

| Tautology   | Contradiction   | Contingency |
| ----------- | --------------- | ----------- |
| Always True | Always False    | Both T/F    |
| Satisfiable | Not Satisfiable | Satisfiable |

##### Logical Implication
- A -> B is logical implication if and only if A -> B is tautology (always true)
##### Logically Equivalence
- A <-> B is logically equivalence if and only if A <-> B is tautology (always true)
<img src="./BIN/Pasted image 20260212003405.png">
- The above image is of de morgan's law

##### Argument
- Argument is valid if conditions where premise are true, conclusion has to true
<img src="./BIN/Pasted image 20260212004547.png">
