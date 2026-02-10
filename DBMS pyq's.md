

The total number of superkeys for a relation with n attributes and one candidate key of size 𝑘 is 2^(n−k)

k -> no. of attributes in candidate key
n -> total no. of attributes in a relation

---

| Feature        | Composite Key                                                  | Compound Key                                                    |
| -------------- | -------------------------------------------------------------- | --------------------------------------------------------------- |
| **Definition** | A primary key/candidate key consisting of two or more columns. | A composite key where _each_ component column is a foreign key. |

---
### A canonical cover (𝐹𝑐) of a functional dependency (FD) set F is simplified, minimal, and equivalent set of dependencies, often called an "irreducible set".

Extraneous attributes in a set of functional dependencies are attributes that can be removed from a dependency without changing the closure (meaning) of that set of dependencies.
<img src="./BIN/Pasted image 20260207194820.png">


---
### Conflict serializability
- If there is loop or cycle in graph then it is conflict serializable
- **conflict**:
	- r-w
	- w-r
	- w-w
<img src="./BIN/Pasted image 20260207230941.png">

<img src="./BIN/Pasted image 20260207234714.png">


<img src="./BIN/Pasted image 20260207235313.png">

### Recall the rules

- **2PL**: all locks acquired before any unlock.
- **Strict 2PL**: _all **exclusive (X)** locks are released only after commit_.
- **Rigorous 2PL**: _all locks (S and X) are released only after commit_.
