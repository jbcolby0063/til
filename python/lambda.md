# Lambda 

```Lambda``` is a single-line anonymous function. 

It doesn't require a name for the function and only needs one expression. 

This type of function becomes handy when you need a function for a short period of time. 

The syntax for ```lambda``` function is:

```lambda argument(s): expression```
```python
# def add(a,b):
#     return a+b

add = lambda a, b: a + b # exactly same as the function above

```

```Lambda``` can be used for sort key:
```python
array = [("Jake", 50), ("Steve", 32), ("David", 74)]

# sort the "array" by the number
print(sorted(array, key=lambda x: x[1])) # [('Steve', 32), ('Jake', 50), ('David', 74)] 
```
```Lambda``` can also be used for map function:
```python
list1 = [1, 2, 3, 4, 5]
list2 = [6, 7, 8, 9, 10]

# apply lambda function to both list1 and list2
result = map(lambda a, b: a + b, list1, list2) # a --> list1 items / b --> list2 items 
print(list(result)) # [7, 9, 11, 13, 15]
```
