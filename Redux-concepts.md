# Core Redux Concepts
[Redux Documentation](https://redux.js.org/introduction/core-concepts)

Redux applications are built upon a one-way flow of data model and are managed by the store:
- The state is the set of data values that describes the application. It is used to render the user interface (UI).
- Users interact with the UI which dispatch actions to the store. An action is an object that expresses a desired change to the state.
- The store generates its next state using a reducer function which receives the most recent action and the current state as inputs.
- Finally, the UI is re-rendered based on the new state of the store and the entire process can begin again.
#
`npm install redux`

`import { createStore } from 'redux';`
## store.js
````
import React from 'react';
import ReactDOM from 'react-dom';
import { createStore } from 'redux';

// REDUX CODE
///////////////////////////////////

const increment = () => {
  return {type: 'increment'} 
}

const decrement = () => { 
  return {type: 'decrement'}
}

const initialState = 0;
const counterReducer = (state = initialState, action) => {
  switch (action.type) {
    case 'increment':
      return state + 1;
    case 'decrement':
      return state - 1;
    default:
      return state; 
  }
} 

const store = createStore(counterReducer);

// REACT CODE
///////////////////////////////////

const render = () => {
  ReactDOM.render(
    <CounterApp 
      state={store.getState()}
    />,
    document.getElementById('root')
  )
}
render();
store.subscribe(render);

function CounterApp(props) {
  
  const state = props.state;

  const onIncrementButtonClicked = () => {
    store.dispatch(increment());
  }
 
  const onDecrementButtonClicked = () => {
    store.dispatch(decrement());
  }
  
  return (   
    <div>
      <h1> {state} </h1>
      <button onClick={onIncrementButtonClicked}>+</button> 
      <button onClick={onDecrementButtonClicked}>-</button>
    </div>
  )
}
````
