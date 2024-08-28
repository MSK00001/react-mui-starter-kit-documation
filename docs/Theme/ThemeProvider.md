---
sidebar_position: 1
---

# Theme 
Themes allow you to change the colors of various components provided by React Navigation. You can use themes to: **Customize the colors match your brand.** Provide  **[light and dark](http://localhost:3000)**. themes based on the time of the day or user preference.

## ThemeProvider

The `ThemeProvider` is used to apply a theme across your entire application. It allows you to define custom colors for components such as navigation bars, buttons, and text, making it easy to ensure consistency in your app's appearance.

## let's Create a theme

 ```jsx
import { createTheme } from '@mui/material/styles';

export const getTheme = (primaryColor, secondaryColor, mode) => {
  return createTheme({
    palette: {
      mode: mode,
      primary: {
        main: primaryColor,
      },
      secondary: {
        main: secondaryColor,
      },
    },
  });
};
``` 
## Wrap App Component with ThemeProvider

Update src/index.js to wrap the App component with `ThemeProvider`.

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";

import App from "./App";
import { ThemeProvider } from "./context/ThemeContext";
const rootElement = document.getElementById("root");
const root = createRoot(rootElement);

root.render(
  <StrictMode>
    <ThemeProvider>
      <App />
    </ThemeProvider>
  </StrictMode>
); 
```






