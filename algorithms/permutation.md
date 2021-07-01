# Permutation 

```Permutation``` is an arrangement of objects in which the order matters. (<-> [Combination](https://github.com/jbcolby0063/til/blob/main/algorithms/combination.md))

For example, "AB" and "BA" are count as different arrangements. 

Python provides ```permutations``` library through ```itertools``` package. This library takes a 
list as an input and returns an object list of tuples that contain all ```permutations```:
```python
from itertools import permutations 

data = ["A", "B", "C"]

result = list(permutations(data, 3)) # permutations of 3
print(result) # [('A', 'B', 'C'), ('A', 'C', 'B'), ('B', 'A', 'C'), ('B', 'C', 'A'), ('C', 'A', 'B'), ('C', 'B', 'A')]
```

You can also generate ```permutation``` with repetitions (e.g. "AA" and "BB" are allowed) by importing ```product```:
```python
from itertools import product

data = ["A", "B", "C"]

result = list(product(data, repeat=2)) # permutations of 2 (with repetition)
print(result) #[('A', 'A'), ('A', 'B'), ('A', 'C'), ('B', 'A'), ('B', 'B'), ('B', 'C'), ('C', 'A'), ('C', 'B'), ('C', 'C')]
```
