---
sidebar_position: 1
---
# Authentication
Authentication is a critical feature in modern web applications, ensuring that users can securely access and manage their data. In your project, the authentication system is designed with the following capabilities:
- **User Registration**: Users can create new accounts with a unique username and password.
- **User Login**: Existing users can log in to their accounts using their credentials.
- User authentication using JWT (JSON Web Tokens)
- User registration with email verification
- Secure storage of user data in Firebase

## Step to Follow Work With JWT token

## 1. User Registration with Email Verification
First, let's handle user registration and email verification:

```jsx
import { getAuth, createUserWithEmailAndPassword, sendEmailVerification } from "firebase/auth";

const auth = getAuth();

const registerUser = async (email, password) => {
  try {
    const userCredential = await createUserWithEmailAndPassword(auth, email, password);
    const user = userCredential.user;

    // Send verification email
    await sendEmailVerification(user);

    console.log("Registration successful! Verification email sent to:", email);
  } catch (error) {
    console.error("Error during registration:", error.message);
  }
};
```
## 2. User Login with JWT Generation
Next, after the user verifies their email, they can log in, and a JWT will be generated:

```jsx
import { signInWithEmailAndPassword } from "firebase/auth";
import jwt from 'jsonwebtoken';

const loginUser = async (email, password) => {
  try {
    const userCredential = await signInWithEmailAndPassword(auth, email, password);
    const user = userCredential.user;

    if (user.emailVerified) {
      // Generate a JWT (in a real application, this would happen on the server)
      const token = jwt.sign({ uid: user.uid, email: user.email }, 'your-secret-key', { expiresIn: '1h' });

      // Store the token (e.g., in localStorage or cookies)
      localStorage.setItem('token', token);

      console.log("Login successful! JWT generated:", token);
    } else {
      console.error("Email not verified. Please verify your email before logging in.");
    }
  } catch (error) {
    console.error("Error during login:", error.message);
  }
};
```
 ## 3. Protecting Routes with JWT
 You can protect your routes by checking for a valid JWT before allowing access:

``` jsx
import { Navigate } from "react-router-dom";
import jwt from 'jsonwebtoken';

const ProtectedRoute = ({ children }) => {
  const token = localStorage.getItem('token');

  if (!token) {
    return <Navigate to="/login" />;
  }

  try {
    jwt.verify(token, 'your-secret-key');
    return children;
  } catch (error) {
    console.error("Invalid token:", error.message);
    return <Navigate to="/login" />;
  }
};

export default ProtectedRoute;
```

## 4. Secure User Data Storage in Firebase
To securely store user data in Firebase, you can use the Firebase Realtime Database or Firestore.

```jsx
import { getFirestore, doc, setDoc, getDoc } from "firebase/firestore"; 

const db = getFirestore();

const saveUserData = async (userId, data) => {
  try {
    await setDoc(doc(db, "users", userId), data);
    console.log("User data saved successfully!");
  } catch (error) {
    console.error("Error saving user data:", error.message);
  }
};

const getUserData = async (userId) => {
  try {
    const docRef = doc(db, "users", userId);
    const docSnap = await getDoc(docRef);

    if (docSnap.exists()) {
      console.log("User data:", docSnap.data());
      return docSnap.data();
    } else {
      console.log("No such document!");
      return null;
    }
  } catch (error) {
    console.error("Error getting user data:", error.message);
  }
};
```






