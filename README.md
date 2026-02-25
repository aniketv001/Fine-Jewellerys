# Fine Jewellery's - E-Commerce Platform

A full-stack e-commerce platform for jewelry shopping with user authentication, cart management, wishlist, and order tracking.

## 🚀 Quick Start

### Prerequisites
- Node.js (v16 or higher)
- npm
- MongoDB Atlas account (or local MongoDB)

### Installation & Setup

1. **Install Frontend Dependencies**
```bash
npm install --legacy-peer-deps
```

2. **Install Backend Dependencies**
```bash
cd server
npm install
cd ..
```

3. **Start Backend Server** (Terminal 1)
```bash
cd server
npm run dev
```

4. **Start Frontend Server** (Terminal 2 - New Window)
```bash
npm run dev
```

5. **Access Application**
- Frontend: http://localhost:8080
- Backend API: http://localhost:5000

## 📋 Detailed Setup Guide

For complete setup instructions on a new PC, see [SETUP_GUIDE.md](./SETUP_GUIDE.md)

## ✨ Features

- 🔐 User Authentication (Login/Signup with JWT)
- 🛍️ Product Browsing with Advanced Filters
- 🛒 Shopping Cart Management
- ❤️ Wishlist (Backend Synced)
- 📦 Order Management & Tracking
- 👤 User Profile Management
- 💳 Checkout Process
- 📱 Fully Responsive Design
- 🎨 Modern UI with Tailwind CSS

## 🛠️ Tech Stack

### Frontend
- React 18
- TypeScript
- Vite
- TailwindCSS
- React Router
- React Query
- Shadcn/ui Components
- Lucide Icons

### Backend
- Node.js
- Express.js
- MongoDB with Mongoose
- JWT Authentication
- bcrypt for Password Hashing
- CORS enabled

## 📁 Project Structure

```
glimmer-grace/
├── src/                    # Frontend source code
│   ├── components/         # React components
│   ├── pages/             # Page components
│   ├── contexts/          # React contexts (Auth, Cart)
│   ├── data/              # Static data
│   └── hooks/             # Custom hooks
├── server/                # Backend source code
│   ├── controllers/       # Route controllers
│   ├── models/           # MongoDB models
│   ├── routes/           # API routes
│   ├── middleware/       # Auth middleware
│   └── server.js         # Express server
├── public/               # Static assets
└── SETUP_GUIDE.md       # Detailed setup instructions
```

## 🔑 Environment Variables

Backend environment variables are in `server/.env`:
```
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
PORT=5000
```

## 📝 Available Scripts

### Frontend
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build

### Backend
- `npm run dev` - Start development server with nodemon
- `npm start` - Start production server

## 🧪 Testing the Application

1. Create a test account via Sign Up
2. Browse products and add to cart
3. Add items to wishlist
4. Complete checkout process
5. View orders in "My Orders"
6. Update profile in "My Account"

## 🐛 Troubleshooting

### Common Issues

**MongoDB Connection Error**
- Verify MongoDB Atlas connection string
- Check IP whitelist in MongoDB Atlas
- Ensure internet connection

**Port Already in Use**
- Stop other applications using ports 5000 or 8080
- Or change ports in configuration files

**Module Not Found**
- Delete `node_modules` and `package-lock.json`
- Reinstall with `npm install --legacy-peer-deps`

**API Connection Failed**
- Ensure backend server is running on port 5000
- Check CORS configuration
- Visit http://localhost:5000/api/health to verify

## 📦 Database Collections

- **users** - User accounts and authentication
- **orders** - Order history and details
- **wishlists** - User wishlist items

## 🔒 Security Features

- Password hashing with bcrypt
- JWT token authentication
- Protected API routes
- Input validation
- CORS configuration

## 🌐 API Endpoints

### Authentication
- `POST /api/auth/signup` - Register new user
- `POST /api/auth/login` - User login
- `GET /api/auth/me` - Get current user
- `PUT /api/auth/update-profile` - Update user profile

### Orders
- `POST /api/orders` - Create new order
- `GET /api/orders` - Get user orders
- `GET /api/orders/:id` - Get single order

### Wishlist
- `GET /api/wishlist` - Get user wishlist
- `POST /api/wishlist` - Add to wishlist
- `DELETE /api/wishlist/:productId` - Remove from wishlist

## 👥 User Roles

- **Customer** - Browse, shop, and manage orders
- **Admin** - (Future feature) Manage products and orders

## 🚀 Deployment

### Frontend
```bash
npm run build
# Deploy the 'dist' folder to your hosting service
```

### Backend
```bash
cd server
npm start
# Deploy to Node.js hosting service (Heroku, Railway, etc.)
```

## 📄 License

This project is private and proprietary.

## 🤝 Contributing

This is a private project. For any questions or issues, contact the development team.

---

**Built with ❤️ for Fine Jewellery's**
