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
2. Selection Sort:
   - repeatedly finds the minimum element from an unsorted array and swap with the element at the beginning
   - time complexity of O(N^2) since it visits all the other elements for each element
   - 3 2 1 0 --> 0 2 1 3 --> 0 1 2 3
   ```python
   array = [7, 5, 9, 0, 3, 1, 6, 2, 4, 8]

   for i in range(len(array)):
       min_index = i
       for j in range(i + 1, len(array)): # reason of complexity N^2
           if array[j] < array[min_index]:
               min_index = j
       array[i], array[min_index] = array[min_index], array[i] # swap the minimum element and the beginning element
   print(array) # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
   ```
3. Insertion Sort:
   - elements from an unsorted array are selected and placed at the correct position. This is repeated until the array becomes sorted. 
   - time complexity is O(N^2). If the array is already almost sorted, the time complexity becomes O(N)
   - 4 3 2 10 --> 3 4 2 10 --> 2 3 4 10
   ```python
   array = [7, 5, 9, 0, 3, 1, 6, 2, 4, 8]

   for i in range(1, len(array)):
       for j in range(i, 0, -1): # from i to 0 index of an array, check each element (reverse order)
           if array[j] < array[j - 1]: # if a element in front is greater than the current element, swap position 
               array[j], array[j - 1] = array[j - 1], array[j]
           else: # if a element in the front is smaller than the current element, stop since all the other elements in front are going to be smaller than the current element
               break 
   print(array) # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
