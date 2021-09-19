# useRef

```useRef``` is a hook that takes only one argument and returns mutable ref object.

The passed argument is initialized in ```.current``` property of ```useRef```, and the return object persists 
for the full lifetime of the component. 

The important part of ```useRef``` is that no matter how many times we change the return object, it will <em>never 
cause our componenet to rerender</em>. This is because ```useRef``` set the object separate from the component render
cycle. 

There are two main uses of ```useRef```:
1. Access the DOM nodes / React elements
```javascript
const inputRef = useRef()

<input type="text" ref={inputRef} /> // inputRef.current refers to this <input> tag (e.g. inputRef.current.value will give you the input value from this tag)
```
2. Persist value 
```javascript
const [name, setName] = useState('')
const prevName = useRef('')

useEffect(() => {
  prevName.current = name
}, [name]) 

// When the {name} state changes and renders, the {prevName.current} will still be previous {name} value
// And after it completes rendering below part, {prevName.current} will change to new {name} value by useEffect()
<div> My name is {name} and it used to be {prevName.current}</div> 
```

