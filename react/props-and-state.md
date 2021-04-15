# Props and State

Props is used when you want to pass the data to the outside component and make that 
component to initialize with the data you passed. 

But the data cannot be modified inside the 
component that is receiving it from outside. 

```JavaScript 
class FirstComponent extends React.Component {    
    render() {    
        return (        
            <SecondComponent msg="passing" />    
        );  
    }
}

const SecondComponent = (props) => {    
    return <p>{props.msg}</p>; 
};
```
State is used when you want to store the data inside the component and keep updating inside using ```setState()``` method.

However, State data cannot be accessed from outside.

```JavaScript
class FirstComponent extends React.Component {    
    constructor(props) {    
        super(props)
        this.state = {      
            msg: "updating"   
        };  
    }    
    
    render() {    
        return ( 
              <div>
                {this.state.msg} 
              </div>
        );  
    }
}
```
