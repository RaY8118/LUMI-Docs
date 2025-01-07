### **Sign-In Flow**

1. The user enters their email and password and clicks **"Sign In."**
2. The **handleLogin()** function in _authService.js_ is triggered, sending a POST request to the `/login` route with the provided credentials.
3. The server validates the credentials:
    - The MongoDB database is queried for the user record.
    - If the user is found, the request proceeds to Firebase Authentication for verification.
4. On successful authentication:
    - User data is fetched and stored in the **UserProvider**, creating a global context for the user session.
    - The user is redirected to _main.jsx_ (Reminders Page).
5. If authentication fails, an error message is displayed on the login page.

### **Sign-Up Flow**

1. The user clicks **"Sign Up"** on the sign-in page and is redirected to the _sign-up.jsx_ screen.
2. The user enters their email, password, role, mobile then clicks **"Sign-Up."**
3. The **handleRegister()** function in _authService.js_ is triggered, sending a POST request to the `/register` route with the provided details.
4. The server processes the registration:
    - The MongoDB database is checked for an existing user with the same email.
    - If no user exists, a new record is created in MongoDB.
    - Firebase Authentication is used to create the user securely.
5. On successful registration:
    - The new user data is saved in the database.
    - The user is automatically authenticated and redirected to _main.jsx_ (Reminders Page).
6. If registration fails (e.g., email already exists), an error message is displayed on the _sign-up.jsx_ page.
### **Reset Password Flow**

1. The user clicks **"Forgot Password"** on the sign-in page and is redirected to the _forgot-password.jsx_ page.
2. The user enters their registered email address and clicks **"Send Reset Link."**
3. The **handleReset()** function in _authService.js_ is triggered, sending a POST request to the `/reset-password` route with the provided email.
4. The server validates the email:
    - Checks the MongoDB database for the user's existence.
    - If the user exists, Firebase Authentication sends a password reset email to the provided address.
5. The user receives an email containing a secure link to reset their password.
    - On clicking the link, the user is redirected to Firebase's password reset page.
6. If the email is not found or if an error occurs during this process, an appropriate error message is displayed on the _forgot-password.jsx_ page.

### **Autofill Credentials Workflow**

1. **Trigger:** The autofill process is initiated when the sign-in page loads or when the user clicks a dedicated autofill button.
2. **Authentication:** Biometric authentication ensures security before fetching saved credentials from `SecureStore`.
3. **Convenience:** Upon successful authentication, securely stored email and password are automatically filled into the sign-in form, streamlining the login process.
### **Flowchart**

[[SignInFlow.jpeg]]
