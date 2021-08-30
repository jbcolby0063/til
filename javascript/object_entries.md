# Object.entries()

```Object.entries()``` is a method that returns keys and values of a given object in ```[key, value]``` array format. 

```javascript
const object1 = {
  a: 'hello',
  b: 'world'
};

console.log(Object.entries(object1)) // [["a", "hello"], ["b", "world"]]
```

It is therefore useful to get both key and value from a certain object.

You can get ```[key, value]``` pairs using for loop:
```javascript
const object1 = {
  a: 'hello',
  b: 'world'
};

for (const [key, value] of Object.entries(object1)) {
  console.log('key: '+ key + '; ' + 'value: ' + value);
}

// output:
// "key: a; value: hello"
// "key: b; value: world"
```
