# Queue 

```Queue``` is a data structure that follows "First In First Out" order.

So a data that comes in first is the first one to leave.

A good example will be a ```queue``` of customers where a customer who came first is served first. 

The opposite of ```queue``` is [stack](https://github.com/jbcolby0063/til/blob/main/algorithms/stack.md).

[![1-6-Mq-og-ES1-Tu-IFxl-C7b-Mc-Xw.png](https://i.postimg.cc/6q90484d/1-6-Mq-og-ES1-Tu-IFxl-C7b-Mc-Xw.png)](https://postimg.cc/ph68gXZT)

Here's a simple code for ```queue```:
```python
from collections import deque # use "deque" library
queue = deque()

queue.append(5) # first in; [5]
queue.append(2) # second in; [5, 2]
queue.append(3) # [5, 2, 3]
queue.append(7) # [5, 2, 3, 7]
queue.popleft() # first out; [2, 3, 7]
queue.append(1) # [2, 3, 7, 1]
queue.append(4) # [2, 3, 7, 1, 4]
queue.popleft() # second out; [3, 7, 1, 4]

print(queue) # deque([3, 7, 1, 4])
queue.reverse() # reverse queue
print(queue) # deque([4, 1, 7, 3])
```
