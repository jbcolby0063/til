# 'Objects are not valid as a React child' Error

```Object are not valid as a React child``` is an error that occurs when you try to render a raw object in React.

```javascript
class App extends Component {
  render() {
    const obj1 = {"A": "hello", "B": "world!"}
    return (
      <div className="App">
        {obj1} // ==> reason of the error (raw object)
      </div>
    )
  }
}
```

You can solve this error by using several methods:

1. Render object as strings using [JSON.stringify()](https://github.com/jbcolby0063/til/blob/main/json/stringify.md):
```javascript
class App extends Component {
  render() {
    const obj1 = {"A": "hello", "B": "world!"}
    return (
      <div className="App">
        {JSON.stringify(obj1)} // output: {"A": "hello", "B": "world!"}
      </div>
    )
  }
}
```
2. Render object properties individually:
```javascript
class App extends Component {
  render() {
    const obj1 = {"A": "hello", "B": "world!"}
    return (
      <div className="App">
        {obj1.A} // output: hello
      </div>
    )
  }
}
```
3.
