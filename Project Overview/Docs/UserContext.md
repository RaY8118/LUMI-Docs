### **Global Context in React Native**

#### **What is Global Context?**

Global Context is a way to manage shared state across your app using React’s `Context API`. It avoids the need for prop drilling by providing a central place to store and access global data, such as user information or application-wide settings.

---

#### **How it Works in App**

1. **User Data Management:**
    
    - The `UserProvider` fetches user data from the backend using the stored token from `SecureStore`.
    - It ensures the user stays logged in and their data is accessible throughout the app.
2. **Authorization Flow:**
    
    - If no token is found or user data cannot be fetched, the app redirects to the login screen (`/sign-in` route).
    - This ensures only authenticated users can access the app’s main features.
3. **State Sharing Across Components:**
    
    - The `UserProvider` wraps the entire app, providing `user`, `setUser`, and `isLoading` as part of the context.
    - Any child component can use these values by calling the `useUser()` hook.
4. **Refetching User Data:**
    
    - A `refetch` function is exposed to reload the user data manually if required (e.g., after profile updates).
5. **Error Handling:**
    
    - The system gracefully handles token absence, API failures, or errors by alerting the user and redirecting to the login screen when necessary.

---

#### **Key Functions in Your Implementation**

- **`fetchUserData()`**:
    
    - Fetches user data using the stored token and updates the context state.
    - Redirects to login on failure.
- **`refetch()`**:
    
    - Reloads the user data by invoking `fetchUserData()` manually, ensuring updated information is available.
- **Context Values:**
    
    - `user`: Stores user information such as name, role, and family ID.
    - `isLoading`: Indicates if user data is being fetched.
    - `setUser`: Allows components to update the user state directly.
    - `fetchUserData` & `refetch`: Provide flexibility to manage user state dynamically.
