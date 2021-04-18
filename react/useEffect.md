# useEffect

```useEffect``` is a react hook that performs 'side effects' in functional components.

```useEffect``` is executed every single time the application renders. It is also executed when the value
in second parameter (dependency) changes. 

There are 3 main ways to use ```useEffect```:
``` javascript
// 1. No Dependency : The useEffect is executed when any component changes
useEffect(() => {});

// 2. Dependency with an empty array : The useEffect is executed only once when it first
// renders because the [] value never changes
useEffect(() => {}, []);

// 3. Dependency with a certain value : The useEffect is executed whenever the value in second 
// parameter changes (in this case, {name} state)
const [name, setName] = useState('Mike');
useEffect(() => {}, [name]);
```
