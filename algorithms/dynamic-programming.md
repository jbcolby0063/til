# Dynamic Programming 
In ```dynamic programming```, you save the result in a separate memory (array, list, ...) and prevent it from being calculated again. 

```Dynamic programming``` can be used when a certain problem meets two conditions:

1. **Optimal Substructure**: Each part of the problem can be solved by combining its small parts.  
2. **Overlapping Subproblem**: Same part of the problem is repeated.

There are 2 methods for ```dynamic programming```:  
1. **Top-Down (Memoization)**
 
    - Save the result in a memory and bring that result back when the same problem appears
    ```python
    
    d = [0] * 100

    def fibo(x):
        if x == 1 or x == 2:
            return 1
        if d[x] != 0: # if this is already calculated
            return d[x] # bring that result from d list
        d[x] = fibo(x - 1) + fibo(x - 2) # if this hasn't been calculated yet, store the result in the list
        return d[x] # and return

    print(fibo(99))
    
    ```
2. **Bottom-Up**

    - Typical ```dynamic programming```
    - Accumulate the result from the bottom (use DP memory)
    ```python
    d = [0] * 100

    d[1] = 1
    d[2] = 1
    n = 99

    for i in range(3, n + 1): # from the bottom (in this case, from d[1] and d[2]), accumulate the result and move up (d[3], d[4], d[5], ...)
        d[i] = d[i - 1] + d[i - 2]

    print(d[n])
    ```
    
