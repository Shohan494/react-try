# react-try-november-2021

```
<div id="p1">
</div>

<div id="p2">
</div>
```

```
function Person(props) {
  return (
    <div className="person">
    <h1>{props.name}</h1>
    <p>Age : {props.age}</p>
    </div>
  );
}

ReactDOM.render(<Person name="Shohan" age="28" />, document.querySelector('#p1'));

ReactDOM.render(<Person name="Another" age="29" />, document.querySelector('#p2'));
```

```
import React from 'react';
import './App.css';

function App() {
  // return (
  //   <div className="App">
  //    <h1>Hello From Shohan!</h1>
  //   </div>
  // );

  // return React.createElement('div', {className: 'App'}, React.createElement('h1', null, 'Hello From Shohan!'));
}

export default App;

```
Person
```
import React from 'react';

const person = (props) => {
    return (
    <div>
    <p>I am a {props.name} and I am {props.age}!</p>
    <p>{props.children}</p>
    </div>
    )
}

export default person;
```

App with state and setState

```
import React, { Component } from 'react';
import './App.css';

import Person from './Person/Person';

// function App() {
//   return (
//     <div className="App">
//      <h1>Hello From Shohan!</h1>
//      <Person name="Shohan" age="28">My Hobbies : Racing</Person>
//     </div>
//   );

//   return React.createElement('div', {className: 'App'}, React.createElement('h1', null, 'Hello From Shohan!'));
// }

class App extends Component {
  state = {
    persons : [
      { name : "Shohan", age: 25} ,
      { name : "Sam", age: 22}
    ]
  }

  switchNameHandler = () => {
    console.log("Clicked!");
    this.setState(
      {
        persons : [
          { name : "Shohanul Alam", age: 29} ,
          { name : "Samual", age: 32}
        ]
      }
    )
  }

  render() {
    return (
    <div className="App">
     <h1>Hello From Shohan!</h1>
     <button onClick={this.switchNameHandler}>Switch Name</button>
     <Person name={this.state.persons[0].name} age={this.state.persons[0].age}>My Hobbies : Racing</Person>
    </div>
    );
  }
}

export default App;

```
Hooks useState

```
import React, { useState } from 'react';
import './App.css';

import Person from './Person/Person';

const App = props => {
  const [ personsState, setPersonsState ] =  useState({
    persons : [
      { name : "Shohan", age: 25},
      { name : "Sam", age: 22}
    ]
  });

const switchNameHandler = () => {
  console.log("Clicked!");
  setPersonsState(
    {
      persons : [
        { name : "Shohanul Alam", age: 29},
        { name : "Samual", age: 32}
      ]
    }
  )
};

  return (
  <div className="App">
    <h1>Hello From Shohan!</h1>
    <button onClick={switchNameHandler}>Switch Name</button>
    <Person name={personsState.persons[0].name} age={personsState.persons[0].age}>My Hobbies : Racing</Person>
    <Person name={personsState.persons[1].name} age={personsState.persons[0].age}>My Hobbies : Racing</Person>

  </div>
  );
}

export default App;

```



