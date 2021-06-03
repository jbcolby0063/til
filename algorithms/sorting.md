# Sorting

```Sorting``` is an algorithm that puts elements of a list in a certain order. 

1. Standard Sort: 
   - use ```sort``` library
   - time complexity of O(NlogN)
   ```python 
   from random import *
   array = []
   for i in range(10):
       array.append(randint(1, 100))
   array.sort()
   print(array) # [1, 7, 11, 28, 61, 62, 79, 82, 82, 90]
    ```
