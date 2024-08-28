---
sidebar_position: 3
---

# use Context
`useContext` is a React Hook that lets you read and subscribe to context from your component.

```bash
const value = useContext(SomeContext)

```
### Example Use Case

`useContext(SomeContext)`

Call `useContext` at the top level of your component to read and subscribe to context.

```jsx
import { useContext } from 'react';

function MyComponent() {
  const theme = useContext(ThemeContext);
  // ...
}

