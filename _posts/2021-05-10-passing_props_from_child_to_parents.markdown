---
layout: post
title:      "React: Passing Props from Child to Parent"
date:       2021-05-10 16:21:50 -0400
permalink:  passing_props_from_child_to_parents
---


When initialliy asked how to pass props from the child to the parent, I responded "Props are only passed from parent to child." I was wrong.  What was even more concerning was that I had already been passing props from child to parent but was unaware of how to explain it. To be honest, due to React’s one-way data flow, it often can be tricky to see how data can flow from child to parent. Let's take a moment to explore how props move from child to parent in React.

So let's imagine, I have data in my child that my parent needs access to, what do I need to do?

**1. Define a callback in my parent which takes the data I need in as a parameter.**

A callback is a function that is passed as an argument to another function, to be “called back” at a later time. 

**2. Pass that callback as a prop to the child **

Parent 
```
import React from 'react';
import Child from './Child'
class App extends React.Component{
      
       state = {
        name: "",
       }
  
    **handleCallback = (childData) =>{
        this.setState({name: childData})
    }**
  
    render(){
        const {name} = this.state;
        return(
            <div>
          **<Child parentCallback = {this.handleCallback}/>**
                {name}
            </div>
        )
    }
}
export default App
```

**3. Call the callback using this.props.[callback] in the child, and pass in the data as the argument.**

Child 
```

import React from 'react'
class Child extends React.Component{
    
    handleOnSubmit = (event) => {
        **this.props.parentCallback(event.target.myname.value);**
        event.preventDefault();
    }
  
    render(){
        return(
        <div>
            <form onSubmit = {this.handleOnSubmit}>
                <input type = "text" 
                name = "yourname" placeholder = "Enter Name"/>
                <br></br>
                <input type = "submit" value = "Submit"/>
                <br></br>
            </form>
        </div>
        )
    }
}
export default Child
```
