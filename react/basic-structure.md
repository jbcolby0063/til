# Basic Structure

Once you ```npm start```, the one that shows on the web browser is the result of "root" element from ```index.html```. 

```html 
<!-- index.html -->
<div id="root"></div> 
``` 

And the code we write on ```App.js``` is rendered to the "root" element by render function in ```index.js```. 
```js
// App.js
class App extends Component {
  render() {
    return (
      <div className="App">
        Hello, React!!
      </div>
    )
  }
}
```
```js
// index.js
ReactDOM.render( 
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
); // renders the App.js to the "root" id in index.html
```

Once the code from ```App.js``` is rendered to the "root" element, our code is displayed.

[![2021-04-10-4-04-14.png](https://i.postimg.cc/W1xtGbTZ/2021-04-10-4-04-14.png)](https://postimg.cc/w1c6Hztx)
