---
sidebar_position: 3
---

# Storage
Storage in web applications is essential for preserving data across sessions, maintaining user preferences, and caching information to enhance performance. There are several storage options available in the browser that you can use within your React application.

## 1.  Local Storage
Local Storage allows you to store data persistently in the browser. The data is stored in key-value pairs and remains accessible even after the browser is closed and reopened.

### Key Characteristics:

- **Persistent Storage**: Data is saved across sessions.
- **Capacity** :  Approximately 5-10 MB per origin.
- **Data Lifetime** : Until explicitly deleted.
- **Accessible From** : Any page within the same domain.

### Example:

```jsx
// Storing data
localStorage.setItem('username', 'JohnDoe');

// Retrieving data
const username = localStorage.getItem('username');

// Removing data
localStorage.removeItem('username');

// Clearing all data
localStorage.clear();
```
### Use Cases:
- Saving user preferences (e.g., theme settings).
- Caching simple data (e.g., form inputs).

## 1. Session Storage
Session Storage is similar to Local Storage, but the data is only available for the duration of the page session. Once the browser tab is closed, the data is deleted.

 #### Key Characteristics:
- **Session-based Storage:** Data is available only during the current session.
- **Data Lifetime:**  Until the tab is closed.
- **Accessible From:** Any page within the same domain.

### Example:

```jsx
// Storing data
sessionStorage.setItem('sessionId', 'abc123');

// Retrieving data
const sessionId = sessionStorage.getItem('sessionId');

// Removing data
sessionStorage.removeItem('sessionId');

// Clearing all data
sessionStorage.clear();
```
### Use Cases:

- Temporary storage for user interactions (e.g., shopping cart items).
- Caching dynamic content (e.g., search results).

## 3. Cookies
Cookies are small pieces of data stored in the browser and sent with every HTTP request to the server. They can be used for session management, tracking, and storing user information.

#### Key Characteristics:
- **Server-side Storage:** Data is stored on the server.
- **Data Lifetime:** Until the cookie expires or is deleted.
- **Accessible From:** Any page within the same domain.
- **HTTP Request/Response:** Sent with every HTTP request to the server.

### Example:

```jsx
// Setting a cookie
document.cookie = "username=JohnDoe; expires=Fri, 31 Dec 2024 12:00:00 UTC; path=/";

// Retrieving a cookie
const cookies = document.cookie.split(';');
const usernameCookie = cookies.find(cookie => cookie.trim().startsWith('username='));

// Deleting a cookie
document.cookie = "username=; expires=Thu, 01 Jan 1970 00:00:00 UTC; path=/;";
```
### Use Cases:
- User authentication and session management.
- Tracking user behavior and preferences.
- Personalization and targeted advertising.


