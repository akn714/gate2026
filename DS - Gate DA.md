
# Data Structures

- Array
- Stack
	- Stack Permutation (n!)
	- Infix to Postfix
	![[Pasted image 20260213212228.png]]
- Queue
	- queue full condition -> `rear == size - 1`
	- circular queue (full condition -> `front == (rear + 1) % maxsize`)
- Hashing
	- Separate Chaining
	- Linear Probing
	- Quadratic Probing
	- Double Hashing
- Linked List
	- reversal of ll
	```python
	def reversal_ll(head):
		prev = None
		curr = head
		while curr:
			next_node = curr.next
			prev = curr
			curr = next_node
		return prev
	```

- Tree
	- **perfect binary tree**
		- all levels are fills completely
		```
		no. of nodes = 2^(h+1) - 1
		h -> height
		```
	- **complete binary tree**
		- fill children from left
	- **strict binary tree / full binary tree**
		- every node has 2 or 0 children
		- should be complete already
- Binary Heap
	- completed binary tree
	- max heap or min heap
- AVL Tree 
	- balanced binary search tree
	- `balance factor = height of left subtree - height of right subtree`
	- balance factor = {-1, 0, 1}
	![[Pasted image 20260213231126.png]]
