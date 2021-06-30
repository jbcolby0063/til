# Combination

```Combination``` is an arrangement of objects in which the order doesn't matter. (<-> [Permutation](https://github.com/jbcolby0063/til/blob/main/algorithms/permutation.md))

For example, "AB" and "BA" are count as same arrangements. 

Python provides ```combinations``` library through ```itertools``` package. This library takes a 
list as an input and returns an object list of tuples that contain all combinations:
```python
from itertools import combinations

data = ["A", "B", "C"]

result = list(combinations(data, 2)) # combination of 2
print(result) # [('A', 'B'), ('A', 'C'), ('B', 'C')]
```
