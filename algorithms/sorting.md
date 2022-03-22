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
C. Insertion Sort:
- each element from an unsorted array is compared with all the elements located to its left and insert at the right position. This is repeated until the array becomes sorted.
- time complexity is O(N^2). However, if the array is already almost sorted, the time complexity becomes O(N) since we do not need to do the comparison if the elements on the left side are already smaller (sorted). 
- 4 3 2 10 --> 3 4 2 10 --> 2 3 4 10
```python
#Python
array = [7, 5, 9, 0, 3, 1, 6, 2, 4, 8]

for i in range(1, len(array)):
    for j in range(i, 0, -1): # from i to 0 index of an array, check each element (reverse order)
        if array[j] < array[j - 1]: # if an element in front is greater than the current element, swap position 
            array[j], array[j - 1] = array[j - 1], array[j]
        else: # if an element in the front is smaller than the current element, stop since all the other elements in front are going to be smaller than the current element
            break 
print(array) # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```
D. Bubble Sort:
- Compares a pair of adjacent elements and swaps right to left if it is smaller.  Goes through all pairs and repeats the process n times to ensure every element has had the chance to move anywhere in the list.
- time complexity is O(N^2) because it visits all pairs of adjacent elements and repeats this process n times. 
- <strong>1</strong> <strong>4</strong> 2 5 8 -> 1 <strong>4</strong> <strong>2</strong> 5 8 -> 1 <strong>2</strong> <strong>4</strong> 5 8 -> 1 2 <strong>4</strong> <strong>5</strong> 8 -> 1 2 4 <strong>5</strong> <strong>8</strong>
```c++
//C++
void bubbleSort(int arr[], int n) 
{ 
    for (int i = 0; i < n-1; i++){ // repeat the process n times
        for(int j = 0; j < n - i - 1; j++){ 
            if(arr[j] > arr[j+1]){ // compare with an adjacent element
                int temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
        }
    }     
      
} 
```

## 2. Divide-and-Conquer Method (usually has O(NlogN) time complexity)
A. Merge Sort:
- splits the array into halves, repeatedly calling itself until the array size is 1 or 2 (recursion).  After this, return up the call stack and apply a “merge” algorithm, which is just reading through the two adjacent halves and selecting the next smallest element from each in order to create the new merged array.
- average time complexity is O(NlogN) since the array is divided into logN levels and merge runs N times each level. The time complexity becomes O(N) when the array is already sorted and all we need to do is just use an in-place strategy since arr1[last] <= arr2[first] (no merge is needed). 
- [Merge Sort Visualization](https://www.youtube.com/watch?v=JSceec-wEyw)
```c++
// C++
void mergeSort(int array[], int const begin, int const end)
{
    if (begin >= end){
        return; // Returns recursively
    }
    auto mid = begin + (end - begin) / 2;
    mergeSort(array, begin, mid); // recursively call itself until size becomes 1
    mergeSort(array, mid + 1, end);
    merge(array, begin, mid, end); // merge two halves
}
```

B. Quick Sort:
- picks the first element in an unsorted array as a pivot and divides the given array based on the selected pivot
- process: pick the first element as a pivot --> from left to right, find an element that is bigger than the pivot --> from right to left, find an element
  that is smaller than the pivot --> swap these two elements' positions --> repeat this until the bigger element position is on the right side of the smaller 
  element position --> place the pivot between them and divide the array into two based on the pivot --> eventually all smaller elements will be placed before    pivot and all bigger elements will be placed after pivot --> do the same process (recursion) with the divided arrays
- <strong>3(pivot)</strong> 2 4 5 1 --> <strong>3(pivot)</strong> 2 <strong>4(bigger)</strong> 5 <strong>1(smaller)</strong> --> <strong>3(pivot)</strong> 2 1 5 4 --> <strong>3(pivot)</strong> 2 <strong>1(smaller)</strong> <strong>5(bigger)</strong> 4 --> 2 1 3 5 4 --> ...
- time complexity of O(NlogN) since it divides the array into logN levels and sorting occurs while doing the partition (or division), which runs in N times each level. But if the array is already almost sorted, quick sort can be inefficient, with 
  O(N^2)
- [Quick Sort Visualization](https://www.youtube.com/watch?v=PgBzjlCcFvc)

Method 1
```python
# Python
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
# Python
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
## 3. Non-comparative Method (usually has O(N + K) time complexity)
A. Counting Sort:
- sorts the elements in an array by counting the number of occurrences of each element 
- create a bucket that can store the number of occurrences for each element (therefore, the size of bucket should be the maximum number of the array) --> visit each element and store the number of times a certain element occurred --> after storing all number of occurrences, modify bucket by adding previous counts --> place the elements in their correct positions based on the bucket
- guarantees the time complexity of O(N + K) if the number of elements are N and maximum is K. However, it can be a memory waste when the elements in the array are just 0 and 999,999 (wasting the memory of bucket from index 1 to index 999,998) 
- [Counting Sort Visualization](https://www.youtube.com/watch?v=7zuGmKfUt7s)
```python
# Python
array = [7, 5, 9, 0, 3, 1, 6, 2, 9, 1, 4, 8, 0, 5, 2]
lst = [0] * (max(array) + 1) # list that will store the data
for i in array:
    lst[i] += 1 # store the number of occurrences for each element
for i in range(len(lst)): 
    for j in range(lst[i]): # print each element based on their number of occurrences
        print(i, end=" ") # 0 0 1 1 2 2 3 4 5 5 6 7 8 9 9 
```

B. Bucket Sort:
- stores the actual element in the bucket rather than just a count and, depending on the number of buckets, it may require a sub-sorting algorithm (e.g. insertion sort) to keep the buckets ordered.
- create bucket with size of maximum value from the given array -> loop over the elements and put them inside the bucket room that corresponds to the key of the element ->  after done looping, go over the buckets and move each elements in order using a sub-sorting algorithm
- time complexity of O(N + K) if the number of elements are N and the maximum value of the array is K (remember the size of bucket was the maximum value of the given array). 
- [Bucket Sort Visualization](https://www.youtube.com/watch?v=VuXbEb5ywrU)
