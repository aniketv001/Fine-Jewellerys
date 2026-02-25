# Fine Jewellery's - Project Setup Guide

This guide will help you set up and run the Fine Jewellery's e-commerce project on a new PC.

## Prerequisites

Before you begin, make sure you have the following installed on your PC:

1. **Node.js** (v16 or higher)
   - Download from: https://nodejs.org/
   - Verify installation: `node --version`

2. **npm** (comes with Node.js)
   - Verify installation: `npm --version`

3. **Git** (optional, for cloning the repository)
   - Download from: https://git-scm.com/

## Project Structure

The project consists of two main parts:
- **Frontend**: React + TypeScript + Vite (main folder)
- **Backend**: Node.js + Express + MongoDB (server folder)

## Step 1: Copy Project Files

1. Copy the entire project folder to your new PC
2. Open a terminal/command prompt in the project root directory

## Step 2: Setup MongoDB

You have two options:

### Option A: Use Existing MongoDB Atlas (Recommended)
The project is already configured to use MongoDB Atlas with the connection string in `server/.env`

### Option B: Use Local MongoDB
1. Install MongoDB Community Edition from: https://www.mongodb.com/try/download/community
2. Update the connection string in `server/.env` to: `mongodb://localhost:27017/jewellery-store`

## Step 3: Install Frontend Dependencies

Open terminal in the project root directory and run:

```bash
npm install --legacy-peer-deps
```

**Note**: The `--legacy-peer-deps` flag is required to resolve dependency conflicts.

## Step 4: Install Backend Dependencies

Navigate to the server folder and install dependencies:

```bash
cd server
npm install
cd ..
```

## Step 5: Configure Environment Variables

The backend environment file is already configured at `server/.env` with:
- MongoDB connection string
- JWT secret
- Port configuration

**Important**: If you want to use a different MongoDB database, update the `MONGODB_URI` in `server/.env`

## Step 6: Start the Backend Server

Open a terminal in the project root and run:

```bash
cd server
npm run dev
```

You should see:
```
✅ MongoDB Connected Successfully
🚀 Server running on http://localhost:5000
```

**Keep this terminal window open** - the backend server needs to keep running.

## Step 7: Start the Frontend Development Server

Open a **NEW** terminal window in the project root directory and run:

```bash
npm run dev
```

You should see:
```
VITE v5.x.x  ready in xxx ms

➜  Local:   http://localhost:8080/
```

## Step 8: Access the Application

Open your web browser and navigate to:
```
http://localhost:8080
```

## Default Ports

- **Frontend**: http://localhost:8080
- **Backend API**: http://localhost:5000

## Testing the Application

### Create a Test Account
1. Click on the user icon in the header
2. Click "Sign Up"
3. Fill in the registration form:
   - Name: Your Name
   - Email: test@example.com
   - Phone: +91 9876543210
   - Password: test123
4. Click "Create Account"

### Test Features
- Browse products
- Add items to cart
- Add items to wishlist
- Place an order
- View orders in "My Orders"
- Update profile in "My Account"

## Troubleshooting

### Issue: "Cannot connect to MongoDB"
**Solution**: 
- Check if MongoDB Atlas connection string is correct in `server/.env`
- Ensure your IP address is whitelisted in MongoDB Atlas
- Check your internet connection

### Issue: "Port 5000 already in use"
**Solution**: 
- Stop any other application using port 5000
- Or change the port in `server/.env`: `PORT=5001`
- Update frontend API calls to use the new port

### Issue: "Port 8080 already in use"
**Solution**: 
- Stop any other application using port 8080
- Or the Vite dev server will automatically suggest another port

### Issue: "Module not found" errors
**Solution**: 
- Delete `node_modules` folder in both root and server directories
- Delete `package-lock.json` files
- Run `npm install --legacy-peer-deps` again in both directories

### Issue: "Failed to fetch" errors in browser
**Solution**: 
- Make sure the backend server is running on http://localhost:5000
- Check browser console for CORS errors
- Verify the backend is accessible by visiting http://localhost:5000/api/health

## Building for Production

### Build Frontend
```bash
npm run build
```
This creates a `dist` folder with production-ready files.

### Run Backend in Production
```bash
cd server
npm start
```

## Important Notes

1. **Keep Both Servers Running**: You need both frontend (port 8080) and backend (port 5000) servers running simultaneously.

2. **MongoDB Connection**: The project uses MongoDB Atlas. Make sure the connection string in `server/.env` is valid and your IP is whitelisted.

3. **Environment Variables**: Never commit the `.env` file to version control if it contains sensitive information.

4. **Legacy Peer Deps**: Always use `npm install --legacy-peer-deps` for the frontend to avoid dependency conflicts.

## Project Features

- ✅ User Authentication (Login/Signup)
- ✅ Product Browsing with Filters
- ✅ Shopping Cart
- ✅ Wishlist (synced with backend)
- ✅ Order Management
- ✅ User Profile Management
- ✅ Responsive Design
- ✅ MongoDB Integration

## Tech Stack

### Frontend
- React 18
- TypeScript
- Vite
- TailwindCSS
- React Router
- React Query
- Shadcn/ui Components

### Backend
- Node.js
- Express.js
- MongoDB with Mongoose
- JWT Authentication
- bcrypt for password hashing

## Support

If you encounter any issues:
1. Check the terminal logs for error messages
2. Verify all dependencies are installed correctly
3. Ensure MongoDB connection is working
4. Check that both servers are running on correct ports

## Quick Start Commands Summary

```bash
# Terminal 1 - Backend
cd server
npm install
npm run dev

# Terminal 2 - Frontend (new terminal window)
npm install --legacy-peer-deps
npm run dev
```

Then open http://localhost:8080 in your browser.

---

**Happy Coding! 🚀**
