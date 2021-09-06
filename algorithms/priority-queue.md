# Priority Queue

```Priority Queue``` is a special queue that dequeues elements based on their level of priorities. 

So an element with higher priority is dequeued before an element with lower priority.

```Priority Queue``` can be solved by using ```Heap``` data structure.

```Heap``` involves ```Min Heap``` and ```Max Heap```. While ```Min Heap``` sorts based on the ascending order, ```Max Heap``` sorts based on
the descending order. 

1. ```Min Heap```:
```python
import heapq # use heapq library 

def heapsort(iterable): # Min Heap Sort
    h = []
    result = []
    for value in iterable: # push every value into heap(h)
        heapq.heappush(h, value)
    for i in range(len(h)): # pop the smallest item from the heap
        result.append(heapq.heappop(h))
    return result

result = heapsort([1, 3, 5, 7, 9, 2, 4, 6, 8, 0])
print(result) # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9] --> ascenting order
```
2. ```Max Heap```:
```python
import heapq

def heapsort(iterable): # Max Heap Sort
    h = []
    result = []
    for value in iterable: 
        heapq.heappush(h, -value) # since python heap library pops the smallest value from heap as default, put minus (-) in front of each values for now, so that we can get descending order later
    for i in range(len(h)):
        result.append(-heapq.heappop(h)) # remove that minus after pop
    return result

result = heapsort([1, 3, 5, 7, 9, 2, 4, 6, 8, 0])
print(result) # [9, 8, 7, 6, 5, 4, 3, 2, 1, 0] # and then the elements are in descending order
```
Since ```Heap``` data strucutre guarantees O(log N) time complexity, it can be effectively used in many different algorithms, including [Dijkstra algorithm](https://github.com/jbcolby0063/til/blob/main/algorithms/dijkstra.md).
