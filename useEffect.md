### example 1

```
import React, {useState, useEffect} from 'react';

const Clicker = () => {
    const [count, setCount]= useState(0);
    useEffect(() =>{
        document.title = `You clicked ${count} times`;
    });
    return (
        <button onClick={()=> setCount(count+1)}>Click me {count}</button>
      );
}

export default Clicker;

`````


### example 2

### SWMovies.js
```
import React, {useState, useEffect} from 'react';
import axios from 'axios';

const SWMovies = () => {
    const [number, setNumber]= useState("");
    const [movie, setMovie]= useState("");

    useEffect(() => {
        async function getData() {
        const response = await axios.get(`https://swapi.co/api/films/${number}`);
        setMovie(response.data);
        }
        getData();
    },[number]);
    return ( 
        <div>
            <h1> Pick a movie</h1>
            <h4>you choose: {movie.title}</h4>
            <h4>{movie.opening_crawl}</h4>
            <select value={number} onChange={e=> setNumber(e.target.value)}>
                <option value="1">1</option>
                <option value="2">2</option>
                <option value="3">3</option>
                <option value="4">4</option>
                <option value="5">5</option>
                <option value="6">6</option>
                <option value="7">7</option>
            </select>
        </div>
     );
}
 
export default SWMovies;

````
