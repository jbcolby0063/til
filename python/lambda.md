# Lambda 

```Lambda``` is a single-line anonymous function. 

It doesn't require a name for the function and only needs one expression. 

This type of function becomes handy when you need a function for a short period of time. 

The syntax for ```lambda``` function is:

```lambda argument(s): expression```

```Lambda``` can be used for sort key:
```python
array = [("Jake", 50), ("Steve", 32), ("David", 74)]

# sort array by the number
print(sorted(array, key=lambda x: x[1])) # [('Steve', 32), ('Jake', 50), ('David', 74)] 
```
