# Binary Search 

```Binary Search``` is an algorithm that searches a location of target value within a sorted array. 

It uses starting point, mid point, and end point to set the searching range. 

If the target value is less than the mid point value, then the mid point becomes the end point for the new searching range, and if 
the target value is greater than the mid point value, then the the mid point becomes the start point for the new searching range. 

You narrow the range down until you find the target value. 

Since ```binary search``` divides the searching range by 2 on every step, the time complexity of this algorithm is O(logN). 

```python
n, target = map(int, input().split()) # 10 16
array = list(map(int, input().split())) # 2 4 6 8 10 12 14 16 18 20

def binary_search(array, target, start, end):
    while start <= end:
        mid = (start + end) // 2 # mid point

        if array[mid] == target: # if this mid point is the target value,
            return mid # return the mid value 
        elif array[mid] > target: # if target value is less than the mid point value,
            end = mid - 1 # set the new end point as current mid value and search the front half
        else: # vice versa
            start = mid + 1 
    return None # if the target value is not in array

result = binary_search(array, target, 0, n - 1)

if result == None:
    print("No target value in array")
else: 
    print(result + 1) # 8
```
Python has its own ```binary search``` library:
```python
# bisect_left(a, x): return the leftmost index position for x in a sorted array a (1 2 ^ 4 4 8)
# bisect_right(a, x): return the rightmost index position for x in a sorted array a (1 2 4 4 ^ 8)

from bisect import bisect_left, bisect_right

a = [1, 2, 4, 4, 8]
x = 4

print(bisect_left(a, x)) # 2
print(bisect_right(a, x)) # 4

# You can use this library to see how many x are in a sorted array a
count_x = bisect_right(a, x) - bisect_left(a, x)
print(count_x) # 2
```
