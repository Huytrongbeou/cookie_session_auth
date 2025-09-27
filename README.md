# Cookie Session Authentication

A simple Node.js authentication system using Express sessions with MongoDB storage.

## What's Inside
- User registration and login
- Password hashing with bcrypt
- Session management with cookies
- MongoDB integration for users and sessions

## Setup
1. Install packages: `npm install`
2. Make sure MongoDB is running on port 27017
3. Start server: `node app.js`
4. Server runs on: http://localhost:3000

## API Endpoints

### Register User
```
POST /auth/register
Content-Type: application/json

{
  "username": "yourname",
  "password": "yourpassword"
}
```

### Login
```
POST /auth/login
Content-Type: application/json

{
  "username": "yourname", 
  "password": "yourpassword"
}
```

### View Profile (Protected)
```
GET /auth/profile
```
*Note: Must be logged in first*

### Logout
```
GET /auth/logout
```

## How It Works
1. **Register** creates a new user with hashed password
2. **Login** checks credentials and creates a session cookie
3. **Profile** shows user info if session exists
4. **Logout** destroys session and clears cookie

## Session Details
- Sessions stored in MongoDB
- Cookies expire after 1 hour
- HTTP-only cookies for security
- Session cookie name: `connect.sid`

## Database
- Database: `sessionAuth` 
- Collections: `users`, `sessions`

## Testing with Postman
1. Register a new user
2. Login with same credentials
3. Access profile (cookie automatically sent)
4. Logout to clear session