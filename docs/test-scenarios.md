# Test Scenarios – Web Application (Portfolio)

Note:
All test scenarios are created for portfolio demonstration purposes only.
They do not represent any real company project.

---

## 1. Authentication – Google Sign In / Sign Up

- User signs up via Google with a new account
- User signs up via Google with an existing account
- User cancels Google consent screen during sign up
- Google authentication fails due to network issue
- User signs in via Google successfully
- Prevent duplicate account creation with same Google account
- User logs in via Google on multiple devices
- System disables Google login when browser does not support Google OAuth
- API test for google login method

---

## 2. Authorization & Session Management

- User session is created after successful login
- User session expires after inactivity
- User logs out successfully
- User accesses protected pages without login

---

## 3. UI / UX Behavior

- Loading indicator is displayed during Google authentication
- Proper error message is shown when sign-in fails
- Google login button is enabled/disabled correctly based on browser support
- UI remains stable when user cancels Google consent

---

## 4. Error Handling & Edge Cases

- Internet disconnects during Google sign-in
- User retries Google login after failure
- Unexpected Google service error is handled gracefully

---

## 5. Regression Scenarios

- Google sign-in works correctly after new release
- Existing authentication flows are not broken by changes
