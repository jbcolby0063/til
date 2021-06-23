# Permutation 

```Permutation``` is an arrangement of objects in which the order matters. 

For example, "AB" and "BA" are count as different arrangements. 

Python provides ```permutations``` library through ```itertools``` package. This library takes a 
list as an input and returns an object list of tuples that contain all permutations:
```python
from itertools import permutations 

data = ["A", "B", "C"]

result = list(permutations(data, 3)) # permutations of 3
print(result) # [('A', 'B', 'C'), ('A', 'C', 'B'), ('B', 'A', 'C'), ('B', 'C', 'A'), ('C', 'A', 'B'), ('C', 'B', 'A')]
```
