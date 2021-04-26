# JSON.stringify()

```JSON.stringify()``` converts JavaScript object to JSON string.

```JSON.stringify(obj, function, space)``` takes three parameters.

1. First parameter is the object that needs to be converted into string. It is required.
2. Second parameter is a function that is used to transform the result. It is optional.
3. Third parameter is a number that is used to indicate how many space characters to use as white space. It is optional.

```javascript 
var obj = { "a":"A", "b":2, "c":"C", "d": 4};

function addNumber(key, value) {
  if (typeof value === "number") {
    return value + 1
  } else {
    return value;
  }
}

var text = JSON.stringify(obj, addNumber, 10); // use addNumber function and 10 white spaces
```
The result will be:
```
"{
          "a": "A",
          "b": 3,
          "c": "C",
          "d": 5
}"
```
