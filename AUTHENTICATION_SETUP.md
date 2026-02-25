# Authentication Setup Guide

## ✅ Complete Authentication System Implemented!

Your Fine Jewellery e-commerce application now has a fully functional authentication system with MongoDB integration.

## 🚀 Quick Start

### 1. Install Backend Dependencies

Open a **NEW terminal** and run:

```bash
cd server
npm install
```

### 2. Start the Backend Server

```bash
npm run dev
```

The server will start on `http://localhost:5000`

You should see:
```
✅ MongoDB Connected Successfully
🚀 Server running on http://localhost:5000
```

### 3. Keep Frontend Running

Your frontend is already running on `http://localhost:8080`

## 📁 What Was Created

### Backend Files (server/)
```
server/
├── .env                          # MongoDB connection & JWT secret
├── package.json                  # Backend dependencies
├── server.js                     # Express server setup
├── models/
│   └── User.js                   # User database model
├── controllers/
│   └── authController.js         # Login/Signup logic
├── routes/
│   └── auth.js                   # API routes
├── middleware/
│   └── auth.js                   # JWT authentication
└── README.md                     # API documentation
```

### Frontend Files
```
src/
├── contexts/
│   └── AuthContext.tsx           # Authentication state management
└── pages/
    └── Auth.tsx                  # Updated login/signup page
```

## 🔐 Features Implemented

### Backend (Node.js + Express + MongoDB)
✅ User Registration (Signup)
✅ User Login
✅ Password Hashing (bcrypt)
✅ JWT Token Generation
✅ Protected Routes
✅ Input Validation
✅ Error Handling
✅ MongoDB Integration

### Frontend (React + TypeScript)
✅ Login Form
✅ Signup Form
✅ Form Validation
✅ Loading States
✅ Error Handling
✅ Token Storage (localStorage)
✅ User State Management
✅ Protected Routes Ready
✅ User Dropdown in Header
✅ Logout Functionality

## 🎯 How to Test

### 1. Create an Account
1. Go to `http://localhost:8080/auth`
2. Click "Sign Up"
3. Fill in:
   - Full Name: Your Name
   - Email: your@email.com
   - Phone: +91 9876543210
   - Password: password123 (min 6 characters)
4. Click "Create Account"
5. You'll be redirected to home page and logged in

### 2. Login
1. Go to `http://localhost:8080/auth`
2. Enter your email and password
3. Click "Sign In"
4. You'll be redirected to home page

### 3. Check User Status
- Look at the header - you'll see your name instead of "ACCOUNT"
- Hover over your name to see dropdown with:
  - My Account
  - My Orders
  - Logout

### 4. Logout
- Hover over your name in header
- Click "Logout"
- You'll be logged out and redirected to home

## 🔧 API Endpoints

### Sign Up
```
POST http://localhost:5000/api/auth/signup
Content-Type: application/json

{
  "name": "John Doe",
  "email": "john@example.com",
  "phone": "+91 9876543210",
  "password": "password123"
}
```

### Login
```
POST http://localhost:5000/api/auth/login
Content-Type: application/json

{
  "email": "john@example.com",
  "password": "password123"
}
```

### Get Current User (Protected)
```
GET http://localhost:5000/api/auth/me
Authorization: Bearer <your_jwt_token>
```

## 💾 Database

Your MongoDB database: `jewellery-store`

Collections:
- `users` - Stores user accounts

User Schema:
```javascript
{
  name: String,
  email: String (unique),
  phone: String,
  password: String (hashed),
  role: String (user/admin),
  isActive: Boolean,
  createdAt: Date
}
```

## 🔒 Security Features

1. **Password Hashing**: Passwords are hashed with bcrypt (12 rounds)
2. **JWT Tokens**: Secure token-based authentication
3. **Token Expiry**: Tokens expire after 30 days
4. **Input Validation**: Email format, password length validation
5. **Protected Routes**: Middleware to protect sensitive endpoints

## 📱 Frontend Integration

### Using Authentication in Components

```typescript
import { useAuth } from "@/contexts/AuthContext";

function MyComponent() {
  const { user, isAuthenticated, logout } = useAuth();

  if (isAuthenticated) {
    return <div>Welcome, {user?.name}!</div>;
  }

  return <div>Please login</div>;
}
```

### Check if User is Logged In
```typescript
const { isAuthenticated } = useAuth();
```

### Get Current User
```typescript
const { user } = useAuth();
// user.name, user.email, user.phone, user.role
```

### Logout
```typescript
const { logout } = useAuth();
logout(); // Clears token and user data
```

## 🐛 Troubleshooting

### Backend won't start
- Make sure MongoDB connection string is correct in `server/.env`
- Check if port 5000 is available
- Run `npm install` in server directory

### Login/Signup not working
- Check if backend server is running on port 5000
- Open browser console for error messages
- Check Network tab in DevTools

### CORS errors
- Backend is configured to accept requests from `http://localhost:8080`
- If using different port, update CORS in `server/server.js`

## 🎉 Success!

Your authentication system is now fully functional! Users can:
- ✅ Create accounts
- ✅ Login securely
- ✅ Stay logged in (token stored)
- ✅ See their name in header
- ✅ Access account features
- ✅ Logout

## 📝 Next Steps

You can now:
1. Add protected routes for checkout
2. Link orders to user accounts
3. Add user profile editing
4. Implement password reset
5. Add admin panel
6. Add email verification

## 🔗 Important URLs

- Frontend: http://localhost:8080
- Backend API: http://localhost:5000
- Login/Signup: http://localhost:8080/auth
- API Health: http://localhost:5000/api/health
