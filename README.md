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
<img width="975" height="981" alt="image" src="https://github.com/user-attachments/assets/033e986b-5ee5-4f4e-ab7e-7c947e7f6c1a" />
### Check in database
<img width="1775" height="1043" alt="image" src="https://github.com/user-attachments/assets/323a0d5b-74b0-4e2c-a0d9-6d6e66e612c5" />

### Login
```
POST /auth/login
Content-Type: application/json

{
  "username": "yourname", 
  "password": "yourpassword"
}
```
<img width="986" height="963" alt="image" src="https://github.com/user-attachments/assets/5a7e8118-7648-4211-a38f-543d9ec64eb2" />
### Check session in database
<img width="1773" height="1046" alt="image" src="https://github.com/user-attachments/assets/4fe88cf1-129b-445a-802c-f4934708c02e" />


### View Profile (Protected)
```
GET /auth/profile
```
*Note: Must be logged in first*
<img width="981" height="919" alt="image" src="https://github.com/user-attachments/assets/973fa2ce-de84-4e24-b5d1-2ed9267a3572" />


### Logout
```
GET /auth/logout
```
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d3776d22-deba-4368-bb5f-ec2bdc849eff" />

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
