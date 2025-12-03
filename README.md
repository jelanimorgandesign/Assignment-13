# Assignment 13 - FastAPI Calculator with JWT Authentication

## Docker Link

[jelanimorgan/assignment_13](https://hub.docker.com/r/jelanimorgan/assignment_13)

## JWT Login & Registration Routes

### /register

- Receives user info (username/email, password)
- Validates (check duplicates, hash password, store in DB)
- Returns a JWT or success response

### /login

- Valid credentials -> return JWT
- Invalid -> 401 Unauthorized

## Front-End Pages

### register.html

- Fields for email, password, (optional) confirm password
- Client-side checks (email format, min password length)
- On success (server responds 200/201), display success or store the JWT

### login.html

- Fields for email, password
- Client-side checks, minimal
- On success, store the JWT or display a success message

## Playwright E2E Tests

### Positive Tests

- Register with valid data (e.g., email format, pass length), confirm success message
- Login with correct credentials, confirm success or token stored

### Negative Tests

- Register with short password -> front-end error or 400 from server, verify UI shows error
- Login with wrong password -> server returns 401, UI shows invalid credentials message
- Ensure tests locate form fields, type invalid/valid data, submit, and check resulting UI states or server responses