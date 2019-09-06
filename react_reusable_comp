###TodoApp.js

```
import React, {useState} from 'react';
import toggleStatus from './hooks/useToggle';

function TodoApp() {
    const [isHappy , toggleIsHappy] = toggleStatus(true);
    const [isNice , toggleIsNice] = toggleStatus(true);
    return (
    <div>
        <h1 onClick={toggleIsHappy}> {isHappy ? "happy" : "sad"} </h1> 
        <h1 onClick={toggleIsNice}> {isNice ? "nice" : "bad"} </h1> 
    </div>
    )
}

export default TodoApp;
```




###useToggle.js
```
import  { useState } from 'react';

function useToggle(initialVal=true){
    const [state, setState]= useState(initialVal);
    const toggle = ()=> {
        setState(!state);
    };
    return [state, toggle];
}

export default useToggle;

```



###App.js
````
import React from 'react';
import TodoApp from './TodoApp'
import togglerStatus from './hooks/useToggle'
import './App.css';

function App() {
  return (
    <TodoApp />
  );
}

export default App;

```
  
