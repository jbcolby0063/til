# Greedy

```Greedy``` is an algorithm that chooses a path that seems to be the best at the moment. 

```Greedy``` algorithm does not guarantee an optimal solution. A path chosen by ```greedy``` might seem like the 
best at the moment, but it might turn out another path is better (more efficient) than the ```greedy``` one. 

Therefore, it is important to analyze the validity of the ```greedy``` method before use. (e.g. Will this guarantee the optimal solution?)

```python
'''
Let's say you have to give the customer $260 change using $100, $20, $10, $5. What would be the 
least number of change you can give? 
'''

n  = 260 
count = 0

# count from dollar with the biggest value first because the bigger value dollar is always a multiple of smaller value dollar
# EX) you can give the customer $100 change with just one $100, instead of five $20
array = [100, 20, 10, 5]

for money in array:
    count += n // money
    n %= money

print(count) # 5
```
