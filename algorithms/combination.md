# Combination

```Combination``` is an arrangement of objects in which the order doesn't matter. (<-> [Permutation](https://github.com/jbcolby0063/til/blob/main/algorithms/permutation.md))

For example, "AB" and "BA" are count as same arrangements. 

Python provides ```combinations``` library through ```itertools``` package. This library takes a 
list as an input and returns an object list of tuples that contains all ```combinations```:
```python
from itertools import combinations

data = ["A", "B", "C"]

result = list(combinations(data, 2)) # combination of 2
print(result) # [('A', 'B'), ('A', 'C'), ('B', 'C')]
```
You can also generate ```combination``` with repetitions (e.g. "AA" and "BB" are allowed) by importing ```combinations_with_replacement```:
```python
from itertools import combinations_with_replacement

data = ["A", "B", "C"]

result = list(combinations_with_replacement(data, 2)) # combinations of 2 (with repetition)
print(result) # [('A', 'A'), ('A', 'B'), ('A', 'C'), ('B', 'B'), ('B', 'C'), ('C', 'C')]
```
