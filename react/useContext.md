# useContext

```useContext``` is a hook that creates global data that can be accessed through specified children 
components. 

In parent component ```myApp```: 
```javascript
import React, { useContext } from 'react';

const MessageContext = React.createContext(); // create the context first

myApp = () => {
    return (
        <MessageContext.Provider value="hello">  // pass the value "hello" to the specified children <Test />
            <Test />
        </MessageContext.Provider>
     );
}
```

In child component ```Test```:
```javascript
import React, { useContext } from 'react';

Test = () => {
    const msg = useContext(MessageContext); // access directly to the passing value "hello" from the parent component
    
    return (
        <div>Message: {msg}</div>
     );
}
```
