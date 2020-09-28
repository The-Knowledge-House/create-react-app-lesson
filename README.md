# Create-React-App-Lesson

To start a React App we will be using create-react-app, since it's the official supported method. 
It creates a modern build without the need for configuration.

## Getting Started

```
npx create-react-app my-app
```

>`npx` is an npm package runner that is used to install and run in a single step

npx is used only once in a React project's life

After your React package has been installed, use `npm start` to start a server that will run your React App

```
cd my-app
npm start
```

The app can be viewed at `https://localhost:3000`

>To stop the server, you just hit ctrl-c in the terminal

The server running is similar to the live-server you have been using for vanilla js, a key feature is the live reload it uses

> We will get a directory of files from create-react-app but we will adjust it to our needs, in other words we will prune it

Starting with the App.js

`import React from 'react';` That first line in `App.js` means that we are importing the React library. 

```
import React from 'react';
import logo from './logo.svg';
import './App.css';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

export default App;
```
As you can see above, there is a functional component `function App()` which declares a React component

`return()`: this is where we are return React component(s) in JSX format

Observing the code inside the return statement, you can see that html is interwined in JSX. As we mentioned in a previous lesson, That will be a commonality in your most of your components.

Also looking at the last line you will see `export default App;`

That means that we are exporting the App function to any other part of the React project that needs it. 
> There can only be one export default per file

## Components and Props

Create a new file called School.js:

```js
import React from 'react';

function School() {
  return (
    <div>
      <h1>School Name</h1>
      <h3>School Location</h3>
    </div>
  );
}

export default School;
```

Let's edit `App.js`:

```js
import React from 'react';
import './App.css';
import Product from './School';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <School/>
      </header>
    </div>
  );
}

export default App;
```
>make it a habit to have your server running via `npm start`
http://localhost:3000 is where you have to go if it hasn't opened up already

## Passing Props
- the components will be modified for props now

```js
import React from 'react';
import './App.css';
import Product from './School';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <School name="The Knowledge House" location="Da Bronx" />
      </header>
    </div>
  );
}

export default App;
```

Now we adjust `School.js` to access the props recieved from the parent `App` component:

```js
import React from 'react';

function Product(props) {
  return (
    <div>
      <h1>{ props.name }</h1>
      <h3>{ props.location }</h3>
    </div>
  );
}

export default Product;
```

Now give it a look on your localhost