# Class Components in the Wild

### React Component model
```js
import React, { Component } from "react";

class Application extends Component {
 render() {
  return <div></div>;
 }
}
```
- must extend the React.Component class
- must override the **render** method 


### Setting State

- Never set state directly
- must use the setState method to change state
- State updates are **asynchronous**
  - question solving: make it depend on the previous one
    ```js
    increment = event => {
    this.setState(previousState => ({
      count: previousState.count + 1
    }));
    };
    ```