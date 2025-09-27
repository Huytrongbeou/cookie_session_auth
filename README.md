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
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/894a7004-ed8b-44c2-a543-b40ccb7abf91" />

### Check in database
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1e169723-571b-4c20-a842-22cfffe51206" />

### Login
```
POST /auth/login
Content-Type: application/json

{
  "username": "yourname", 
  "password": "yourpassword"
}
```
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/eb8fbe71-21fa-4c5d-9a6e-c79109b10666" />
###Cookie
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f39c0137-360b-4493-9285-528c456c40f1" />

### Check session in database
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/68fe5854-780f-4d5c-859f-310068e8f358" />

### View Profile (Protected)
```
GET /auth/profile
```
*Note: Must be logged in first*
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e5d5c3ab-d7af-4452-9aa6-4cd2a6f5e506" />


### Logout
```
GET /auth/logout
```
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4ad7b5bc-b132-4b62-9270-5214770593a5" />
### Check cookie and session after logout
<img width="1920" height="1077" alt="image" src="https://github.com/user-attachments/assets/b3ae639f-3167-4c3e-93f9-6f83e72dc782" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4f96668d-7c62-4266-8bfe-24891ef22a66" />

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
