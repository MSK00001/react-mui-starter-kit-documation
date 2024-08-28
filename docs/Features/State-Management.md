---
sidebar_position: 2
---

# State Management 

State management in React is crucial for managing the application state, ensuring that data flows correctly between components. Here are some popular methods to handle state management in React:

## 1. Local State

Local state is managed within a single component. You can use the `useState` hook to create state variables.

### Example:

```jsx
import React, { useState } from 'react';

export default function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
}
```
## Explanation:
### 1. State Initialization:
The `useState` hook initializes the `count` state variable to `0`. It returns an array with two elements:

- The current state (`count`).
- A function to update this state (`setCount`).

### 2. State Update:
The `handleClick` function is called when the button is clicked. This function updates the state using the `setCount` function, which triggers a re-render of the component with the new `count` value.

### 3. Rendering
The component renders the current count inside a <`p`> tag. Each time the button is clicked, the count is incremented, and the component re-renders with the updated count.