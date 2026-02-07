
### Always take int of 2 bytes

---
#### pointer
```c
i[arr] = arr[i]

char* p = "a_string";

2[p] == p[2] == 's'

// and in 2 d array:
a[][] = {{1,2,3}, {3,5,6}}
*(*(a + i) + j) == a[i][j]
```
since, `2[p] == *(2 + p) == *(p + 2) == p[2]`

```c
#include <stdio.h>

int main() {
    int a[2][3] = {{1,2,3},{4,5,6}};
    printf("%d\n", **a); // **a = a[0][0] = 1
}
```
---
### Ascii A = 65, a = 97

#### A dangling pointer is  a pointer that continues to reference a memory address after that memory has been deallocated or freed

#### malloc() allocated the memory from heap

#### unsigned int stores zero and positive numbers only

---
#### static variables
- Static variables are shared across calls of the SAME function,
- but NOT across DIFFERENT functions unless they’re global

So:
- Same function + recursion → same static variable
- Different functions → different static variables (even if names match)

```c
void main(){
	static int a = 1;
	// static int a = 3; // gives error
	if (True) {
		static int a = 6;
		printf("%d", a); // 6
	}
	printf("%d", a); // 1
	// Note: the 'static int a = 6' doesn't updated the outer a
}
```

---
#### Bit wise shift
```c
a >> k => a/(2^k)

// eg.
5 >> 1 == 2
6 >> 1 == 3
10 >> 2 == 2
```
