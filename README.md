# React Auto Context Creations

A simple React utility for automatic context creation

Install with [npm](https://www.npmjs.com/), [Bower](https://bower.io/), or [Yarn](https://yarnpkg.com/):

npm:

```sh
npm install react-auto-context --save
```

Bower:

```sh
bower install react-auto-context --save
```

Yarn (note that `yarn add` automatically saves the package to the `dependencies` in `package.json`):

```sh
yarn add react-auto-context
```

Use with [React.js](https://reactjs.org/):

## Usage

The `react-auto-context` utility is a function that take 3 arguments and it return the Context And The Provider

### The first argument is the reducer function which should be like that

```js
function reducer(state, action) {
  switch (action.type) {
    case "UPDATE_USER":
      return { user: action.user };
    default:
      return state;
  }
}
```

### The second argument is an object that contains actions that you want to perform And Each Function mapped to a key of the object should be getting dispatch function as an argument and it return function that dispatch the desired action with an object that reducer will receive to update the state

```js
function updateUser(dispatch){
  return function () {
    dispatch({type: 'UPDATE_USER', user: {'name':'Jane Doe'})
  }
}
```

### For passing dynamic arguments when calling dispatch to receive in the reudcer

```js
function updateUser(dispatch){
  return function (name) {
    dispatch({type: UPDATE_USER, user: {name})
  }
}
```

### The third argument is the initialValue that the reducer will be called for the first time

```js
import contextCreation from "react-auto-context";

const { Context, Provider } = contextCreation(
  reducer,
  { updateUser },
  { user: "Mohamed" }
);
```

# react-auto-context
# react-auto-context
# react-auto-context
