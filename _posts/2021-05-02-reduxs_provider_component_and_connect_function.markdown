---
layout: post
title:      " Redux's Provider Component & Connect function"
date:       2021-05-02 12:13:25 +0000
permalink:  reduxs_provider_component_and_connect_function
---


In order to master redux, it is vitally important that you have a clear understanding of how to pass data from the Redux store throughtout your application. Learning how to use the Provider Component and call the connect function are therefore essential to understanding Redux. The Provider Component makes the Redux store(global state) available to any nested components that may need it. After inmporting Provider from react-redux, The Provider Component connects to a root component(usually <App/>) and waits for a nested component to connect to the store. 

**How do you use the Provider Component?**

**Provider Example**

```
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';
import combineReducers from './reducers/index'
import { createStore } from 'redux';
import { Provider } from 'react-redux';

const store = createStore(combineReducers)

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById('root')
);
```

**How do you use the Connect function?**

Here is where the connect function comes in. First you have to import connect from react-redux. The you can call it by adding the connect function to the export default. The connect function returns a copy of the component thay wraps the initial component and passes in the data from the store. Depending on whether you call connect with mapStateToProps or mapDispatchToProps determines whether you can access the state or make a copy of it to manipulate. 

**Connect Example**
```
import React, { Component } from 'react';
import { connect } from 'react-redux';
import './App.css';

class App extends Component {
  render(){
    return (
      <div className="App">
          <p>Count is now of: {this.props.counter} </p>
      </div>
    );
  }
}

const mapStateToProps = state => ({ counter: state.counterReducer.counter })

export default connect(mapStateToProps)(App);
```


**Why do this rather than continuing to pass data down data via props?**

It is recommended that you use the Provider Component and the Connect function instead of passing data down via props because the latter approach can become messy the bigger you scale your application. Passing down information that way is referred to as propdrilling and is highly discouraged. 
