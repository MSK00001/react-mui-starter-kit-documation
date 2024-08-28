---
sidebar_position: 2
---

# use Effect
`useEffect` is a React Hook that lets you synchronize a component with an external system.

```bash
useEffect(setup, dependencies?)
```

## Example :

## 1. Using `useEffect` with Dependencies
In this example, the effect runs every time the `count` state changes.


```jsx
import React, { useState, useEffect } from 'react';

const Counter = () => {
    const [count, setCount] = useState(0);

    useEffect(() => {
        console.log(`Count has changed to: ${count}`);
        
        // Cleanup function (optional)
        return () => {
            console.log(`Cleaning up count: ${count}`);
        };
    }, [count]); // Effect runs when count changes

    return (
        <div>
            <p>Count: {count}</p>
            <button onClick={() => setCount(count + 1)}>Increment</button>
        </div>
    );
};

export default Counter;
```
## 2. Using `useEffect` without Dependencies
When the dependencies array is empty, the effect runs only once, after the initial render.

```jsx
import React, { useState, useEffect } from 'react';

const Counter = () => {
    const [count, setCount] = useState(0);

    useEffect(() => {
        console.log(`Count has changed to: ${count}`);
        
        // Cleanup function (optional)
        return () => {
            console.log(`Cleaning up count: ${count}`);
        };
    }, [count]); // Effect runs when count changes

    return (
        <div>
            <p>Count: {count}</p>
            <button onClick={() => setCount(count + 1)}>Increment</button>
        </div>
    );
};

export default Counter;
```
## Returns 
`useEffect` returns `undefined`.

## Usage 
