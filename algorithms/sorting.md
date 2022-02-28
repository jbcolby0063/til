# Sorting Algorithms

```Sorting``` is an algorithm that puts elements of a list in a certain order. 

There are various sorting algorithms that use different design methods.

## 1. Simple/Iterative Method (usually has O(N^2) time complexity)
 A. Standard Sort: 
 - use ```sort``` library (for Python)
 - time complexity of O(NlogN)
```python 
# Python
from random import *
array = []
for i in range(10):
    array.append(randint(1, 100))
array.sort()
print(array) # [1, 7, 11, 28, 61, 62, 79, 82, 82, 90]
```
B. Selection Sort:
- repeatedly finds the minimum element from an unsorted array and swap with the element at the front. At each step, shrink the unsorted part and consider the elements moved to the front as belonging to the sorted part.
- time complexity of O(N^2) since it visits all the other elements on each step
- 3 2 1 0 --> 0 2 1 3 --> 0 1 2 3
```python
#Python
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
   - elements from an unsorted array are selected and placed at the right position. This is repeated until the array becomes sorted. 
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
   ```
4. Quick Sort:
   - picks the first element in an unsorted array as a pivot and divides the given array based on the selected pivot
   - process: pick the first element as a pivot --> from left to right, find an element that is bigger than the pivot --> from right to left, find an element
     that is smaller than the pivot --> swap these two elements' positions --> repeat this until the bigger element position is on the right side of the smaller 
     element position --> place the pivot between them and divide the array around the pivot --> eventually all smaller elements will be placed before pivot and
     all bigger elements will be placed after pivot --> do the same thing with the divided arrays
   - 3(pivot) 2 4 5 1 --> 3(pivot) 2 4(bigger) 5 1(smaller) --> 3(pivot) 2 1 5 4 --> 3(pivot) 2 1(smaller) 5(bigger) 4 --> 2 1 3 5 4
   - time complexity of O(NlogN) since it divides the array by half every time. But if the array is already almost sorted, quick sort can be inefficient, with 
     O(N^2)
     
   Method 1
   ```python
   array = [5, 7, 9, 0, 3, 1, 6, 2, 4, 8]

   def quick_sort(array):
       if len(array) <= 1: # if there is nothing to sort in the array 
           return array
       pivot = array[0]
       tail = array[1:]
       left = [x for x in tail if pivot > x] # elements smaller than pivot
       right = [x for x in tail if pivot < x] # elements bigger than pivot 

       return quick_sort(left) + [pivot] + quick_sort(right) # use recursive function for divided arrays 

   print(quick_sort(array)) # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
   ```
   Method 2
   ```python
   array = [5, 7, 9, 0, 3, 1, 6, 2, 4, 8]

   def quick_sort(array, start, end):
       if start >= end: # if there is nothing to sort
           return 
       pivot = start
       left = start + 1
       right = end
       while left <= right: # repeat until the bigger element position is on the right side of the smaller element position
           while(left <= end and array[pivot] >= array[left]): # find an element that is bigger than pivot
               left += 1
           while(right > start and array[pivot] <= array[right]): # find an element that is smaller than pivot
               right -= 1
           if left > right: # if the bigger element position is on the right side of the smaller element position
               array[right], array[pivot] = array[pivot], array[right] # place pivot between them
           else: # if not, switch bigger element and smaller element positions 
               array[right], array[left] = array[left], array[right]
       # divide the array 
       quick_sort(array, start, right - 1)
       quick_sort(array, right + 1, end)

   quick_sort(array, 0, len(array) - 1)
   print(array) # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
   ```
5. Counting Sort:
   - sorts an element in an array by counting the number of occurrences of each element 
   - guarantees the time complexity of O(N + K) if the number of elements are N and maximum is K. However, it can be a memory waste when the elements in the array are just 0 and 999,999
   - create a list that can store the number of occurrences for each element --> visit each element and store the number of times a certain element occurred --> after storing all data, print each element based on their number of occurrences
   ```python
   array = [7, 5, 9, 0, 3, 1, 6, 2, 9, 1, 4, 8, 0, 5, 2]
   lst = [0] * (max(array) + 1) # list that will store the data
   for i in array:
       lst[i] += 1 # store the number of occurrences for each element
   for i in range(len(lst)): 
       for j in range(lst[i]): # print each element based on their number of occurrences
           print(i, end=" ") # 0 0 1 1 2 2 3 4 5 5 6 7 8 9 9 
   ```
