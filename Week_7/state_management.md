# Complex State Mangagement

### Stale state:
- some previous data which didnt get update
- use **prev** to aovid

### sReducer:
- a brunch of values --> take actions --> from a new Value
- **pure functions**: priditable function, no side effects

```js
const arr = [1, 2, 3];
// get the sum of them
// do a for loop
```

- and this _accumulator 累加器_ is a **Reducer Pattern**

```js
// another way writing this
let result = arr.reduce((accumulator, value) => {
  return accumulator + value;
  // accumulator presents the previous value
}, 0);
// this means starting at index 0
```

### the reason we dont put the reducer inside the function
- can be exporteds
- save computer memories: it will re-run if it's in the function when it renders
- its a pure function and doesnt depend on other functions

### Dispatcher
- takes the actions and from the state for users
- reduce the complexity of actions
- the **reducer** returns to us; also it passes data to reducers
- the part of **userReducer hook**
- can be any name

### Lookup
- similar with _Switch and If Loop_
- deals with different cases but no defualt case at the end
- needs have more functions to deal with default cases

### value returned
- { true && true && 5 } --> 5
- { 5 || 6 } --> 5

### frament:
- a fake react eleemtn to get ride of something

### Web Socket Server
- handles web sockets


# NEED TO KNOW
- need to rewatch the video:
  1. 15-20 mins before the break for LookUp and Dispathcer
  2. the last 20 mins
  3. the questions form Max
- datahelper()
- web socket server
  - socket.io
  - web socket represent one user