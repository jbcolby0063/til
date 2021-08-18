# React Router 

React Router renders certain components to display by just using its route in the URL (```/``` for homepage, ```/about``` for about page, ...). 

This allows a website to run multiple components in a single page. 

In order to use it, you need to install ```react-router-dom``` using NPM:
```shell
npm install react-router-dom
```
And then you can use it by importing BrowserRouter, Route, Switch from ```react-router-dom```:
```javascript
import { BrowserRouter, Route, Switch } from 'react-router-dom';
import Home from './components/Home'; // make sure to import the components
import About from './components/About';
import Shop from './components/Shop';

// BrowseRouter : Everything that needs to get rendered goes inside <BrowserRouter>
// Switch : Ensure only one component is rendered at a time
// Route : Links for components. Indicate which component to load by using path=" ". Add exact if you want to load just "/".

function App() {
  return (
    <BrowserRouter> 
        <Switch>
          <Route exact path="/" component={Home} /> 
          <Route path="/about" component={About} />
          <Route path="/shop" component={Shop} />
        </Switch>
    </BrowserRouter>
  )
}
```
Now, you can access to each component by using ```Link```:
```javascript
// In Home component 
import { Link } from 'react-router-dom'

<Link to="/about">About Us</Link>
```
You can access history instances using ```useHistory```:
```javascript 
import { useHistory } from 'react-router-dom'

function Home() {
  const history = useHistory();
  
  function handleClick() {
    history.push('/about'); // go straight to '/about' page once the button is clicked
  }

  return (
    <button type="button" onClick={handleClick}> About Us </button>
   );
}
```
In some cases, when you want to restrict users from accessing the home page without log in, you can simply use ```Redirect```:
```javascript
import { Redirect } from 'react-router-dom'

isLoggedIn ? <Component /> : <Redirect to="/login" /> // if user is not logged in, then redirect to login page and restrict the user's access to home page
```
