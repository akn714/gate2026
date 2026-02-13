
### Operator Precedence
![[Pasted image 20260213162918.png]]

##### //
```python
5 // 2 => floor value => 2
```

##### Bit-wise shift
```python
# Left shift
a << h => a * 2^n
2 << 3 => 2 * 2^3 = 16

# Right shift
a >> h => a // 2^n
4 >> 2 => 4 // 2^2 = 2
```

##### ~x -> 2's compliment of x
```python
~x => -(x+1)

~3 => -4
```

### Data types
Python is dynamically typed language.

- **Integer is immutable** -> everytime a new memory is allocated with an integer is updated
- **String is orderd**
	- immutable
	- slicing `a[0:3]`, `a[0:5:2]` (0 is included, 3 and 5 are excluded)
	- `a[::-1]` -> string in reverse order
	![[Pasted image 20260213165640.png]]
- **List**
	- mutable
	- ordered
	- slicing
	- `append(values`, `extend(iteratable)`, `insert(index, value)`
	![[Pasted image 20260213200543.png]]
- **Tuple** - (1,2,4) (set)
	- ordered, immutable, indexing, slicing
	- Duplicate values allowed
	- Heterogeneous - (strings, integers, floats, etc.)
- **Set**
	- No duplicate
	- mutable
	- unordered
	- set can have only immutable values
- **Frozen set**
	- same as set but it is immutable
- **Dictionary**
	- mutable
	- keys should be unique
	- `d.keys()` -> return only keys
	- `d.values()` -> return only values
	- `d.items()` -> return key-values  pairs

#### Shallow copy & Deep copy

##### Shallow Copy
- make a new outer structure, but internal things point to same arrays
##### Deep Copy
- completely make a new copy

```python
a = [ [1,2], [3,4] ]

# shallow copy
b = a
c = a[:]
d = a.copy()

import copy
e = copy.copy()

# deep copy
f = copy.deepcopy()
```
![[Pasted image 20260213192020.png]]

### Functions
- default values are initialized only once, after that same values is used
```python
def func(a, b=[]):
	b.append(a)

func(10) # b = [10]
func(20) # b = [10, 20]
```

#### Match Case Statement
```python
def check_number(x): # x can be any data type
    match x:
        case 10:
            print("It's 10")
        case 20:
            print("It's 20")
        case _:
            print("It's neither 10 nor 20")

check_number(10) # It's 10
check_number(30) # It's neither 10 nor 20
```

