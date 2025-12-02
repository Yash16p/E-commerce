# E-commerce Website - MERN Stack

A full-stack e-commerce web application built with the MERN stack (MongoDB, Express.js, React, Node.js). This project features a modern, responsive design with complete shopping functionality including user authentication, product browsing, cart management, favorites, and order processing.

**Created by: Yash Pandey**

---

## 📋 Table of Contents

- [Features](#-features)
- [Technology Stack](#-technology-stack)
- [Project Structure](#-project-structure)
- [Prerequisites](#-prerequisites)
- [Installation & Setup](#-installation--setup)
- [Environment Variables](#-environment-variables)
- [Running the Application](#-running-the-application)
- [API Documentation](#-api-documentation)
- [Frontend Routes](#-frontend-routes)
- [Database Models](#-database-models)
- [License](#-license)

---

## ✨ Features

### User Features
- **User Authentication**: Secure registration and login with JWT tokens
- **Product Catalog**: Browse products with search and filter capabilities
- **Product Details**: View detailed information about each product
- **Shopping Cart**: Add, remove, and manage items in cart
- **Favorites/Wishlist**: Save favorite products for later
- **Order Management**: Place orders and view order history
- **Responsive Design**: Fully responsive UI that works on all devices

### Technical Features
- JWT-based authentication with protected routes
- Redux Toolkit for state management
- Redux Persist for persistent state
- Material-UI components for modern UI
- RESTful API architecture
- MongoDB database with Mongoose ODM
- Password encryption with bcrypt
- CORS enabled for cross-origin requests

---

## 🛠 Technology Stack

### Frontend
- **React** 18.2.0 - UI library
- **Redux Toolkit** 2.2.1 - State management
- **Redux Persist** 6.0.0 - Persistent state
- **React Router DOM** 6.22.3 - Client-side routing
- **Material-UI** 5.15.13 - UI components
- **Styled Components** 6.1.8 - CSS-in-JS styling
- **Axios** 1.6.8 - HTTP client

### Backend
- **Node.js** - Runtime environment
- **Express.js** 4.18.3 - Web framework
- **MongoDB** - NoSQL database
- **Mongoose** 8.2.2 - MongoDB ODM
- **JWT** 9.0.2 - Authentication tokens
- **Bcrypt** 5.1.1 - Password hashing
- **Dotenv** 16.4.5 - Environment variables
- **Nodemon** 3.1.0 - Development server

---

## 📁 Project Structure

```
E-commerce-website/
├── Ecomerce-website-main/
│   ├── client/                    # React frontend
│   │   ├── public/               # Static files
│   │   ├── src/
│   │   │   ├── api/              # API integration
│   │   │   ├── components/       # Reusable components
│   │   │   │   ├── cards/        # Product cards
│   │   │   │   ├── Button.jsx
│   │   │   │   ├── Navbar.jsx
│   │   │   │   ├── SignIn.jsx
│   │   │   │   ├── SignUp.jsx
│   │   │   │   ├── TextInput.jsx
│   │   │   │   └── ToastMessage.jsx
│   │   │   ├── pages/            # Page components
│   │   │   │   ├── Authentication.jsx
│   │   │   │   ├── Cart.jsx
│   │   │   │   ├── Favourite.jsx
│   │   │   │   ├── Home.jsx
│   │   │   │   ├── NewArrival.jsx
│   │   │   │   ├── ProductDetails.jsx
│   │   │   │   └── ShopListing.jsx
│   │   │   ├── redux/            # Redux store & reducers
│   │   │   ├── utils/            # Utilities & themes
│   │   │   ├── App.js            # Main app component
│   │   │   └── index.js          # Entry point
│   │   └── package.json
│   │
│   └── server/                    # Express backend
│       ├── controllers/          # Business logic
│       │   ├── Products.js
│       │   └── User.js
│       ├── middleware/           # Custom middleware
│       │   └── verifyToken.js
│       ├── models/               # Database schemas
│       │   ├── Orders.js
│       │   ├── Products.js
│       │   └── User.js
│       ├── routes/               # API routes
│       │   ├── Products.js
│       │   └── User.js
│       ├── .env                  # Environment variables
│       ├── error.js              # Error handling
│       ├── index.js              # Server entry point
│       └── package.json
│
└── README.md                      # This file
```

---

## 📦 Prerequisites

Before running this project, make sure you have the following installed:

- **Node.js** (v14 or higher) - [Download](https://nodejs.org/)
- **npm** (comes with Node.js)
- **MongoDB** - Choose one:
  - Local MongoDB - [Download](https://www.mongodb.com/try/download/community)
  - MongoDB Atlas (Cloud) - [Free Tier](https://www.mongodb.com/cloud/atlas)

---

## 🚀 Installation & Setup

### 1. Clone the Repository

```bash
git clone <repository-url>
cd E-commerce-website
```

### 2. Install Backend Dependencies

```bash
cd Ecomerce-website-main/server
npm install
```

### 3. Install Frontend Dependencies

```bash
cd ../client
npm install
```

---

## 🔐 Environment Variables

Create a `.env` file in the `server` directory with the following variables:

```env
MONGO_DB=mongodb://localhost:27017/ecommerce
JWT=your_jwt_secret_key_here_change_this_in_production
PORT=8080
```

**Important**: Change the JWT secret to a strong, random string in production!

### MongoDB Connection Options:

**Local MongoDB:**
```env
MONGO_DB=mongodb://localhost:27017/ecommerce
```

**MongoDB Atlas:**
```env
MONGO_DB=mongodb+srv://<username>:<password>@cluster.mongodb.net/ecommerce?retryWrites=true&w=majority
```

---

## ▶️ Running the Application

### Start the Backend Server

Open a terminal and run:

```bash
cd Ecomerce-website-main/server
npm start
```

The server will start on **http://localhost:8080**

### Start the Frontend

Open a **NEW** terminal and run:

```bash
cd Ecomerce-website-main/client
npm start
```

The client will start on **http://localhost:3000**

The application will automatically open in your default browser.

---

## 📡 API Documentation

### Base URL
```
http://localhost:8080
```

### Authentication Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/api/user/signup` | Register new user | No |
| POST | `/api/user/signin` | Login user | No |

**Signup Request Body:**
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password123"
}
```

**Signin Request Body:**
```json
{
  "email": "john@example.com",
  "password": "password123"
}
```

### Product Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/api/products/` | Get all products | No |
| GET | `/api/products/:id` | Get product by ID | No |
| POST | `/api/products/add` | Add new product | No |

### Cart Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/api/user/cart` | Get user's cart items | Yes |
| POST | `/api/user/cart` | Add item to cart | Yes |
| PATCH | `/api/user/cart` | Remove item from cart | Yes |

**Add to Cart Request Body:**
```json
{
  "productId": "product_id_here",
  "quantity": 1
}
```

### Order Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/api/user/order` | Get user's orders | Yes |
| POST | `/api/user/order` | Place new order | Yes |

### Favorites Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/api/user/favorite` | Get user's favorites | Yes |
| POST | `/api/user/favorite` | Add to favorites | Yes |
| PATCH | `/api/user/favorite` | Remove from favorites | Yes |

### Authentication Header

For protected routes, include JWT token in headers:
```
Authorization: Bearer <your_jwt_token>
```

---

## 🗺 Frontend Routes

| Route | Component | Description |
|-------|-----------|-------------|
| `/` | Home | Landing page with featured products |
| `/shop` | ShopListing | Browse all products |
| `/shop/:id` | ProductDetails | View product details |
| `/cart` | Cart | Shopping cart |
| `/favorite` | Favourite | Wishlist/favorites |

---

## 🗄 Database Models

### User Model
```javascript
{
  name: String,
  email: String (unique),
  password: String (hashed),
  img: String,
  cart: [{ product: ObjectId, quantity: Number }],
  favorites: [ObjectId],
  createdAt: Date,
  updatedAt: Date
}
```

### Product Model
```javascript
{
  name: String,
  description: String,
  price: Number,
  img: String,
  category: String,
  tags: [String],
  sizes: [String],
  createdAt: Date,
  updatedAt: Date
}
```

### Order Model
```javascript
{
  user: ObjectId,
  products: [{
    product: ObjectId,
    quantity: Number
  }],
  totalAmount: Number,
  status: String,
  createdAt: Date,
  updatedAt: Date
}
```

---

## 🎨 Key Features Implementation

### State Management
- Redux Toolkit for centralized state management
- Redux Persist for maintaining state across sessions
- Separate slices for user, products, and cart

### Authentication Flow
1. User registers/logs in
2. Server validates credentials
3. JWT token generated and sent to client
4. Token stored in Redux and localStorage
5. Token included in subsequent API requests
6. Middleware verifies token for protected routes

### Shopping Flow
1. Browse products on home/shop pages
2. View product details
3. Add to cart or favorites
4. Review cart
5. Place order
6. View order history

---

## 🔧 Development Scripts

### Backend
```bash
npm start          # Start server with nodemon (auto-reload)
```

### Frontend
```bash
npm start          # Start development server
npm run build      # Build for production
npm test           # Run tests
```

---

## 🐛 Troubleshooting

### MongoDB Connection Issues
- Ensure MongoDB is running locally or Atlas connection string is correct
- Check firewall settings
- Verify network access in MongoDB Atlas

### Port Already in Use
- Backend: Change PORT in `.env` file
- Frontend: React will prompt to use different port

### CORS Errors
- Ensure CORS is enabled in server
- Check API base URL in frontend

---

## 📝 License

MIT License

---

## 👤 Author

**Yash Pandey**

---

## 🙏 Acknowledgments

- Built with MERN stack technologies
- Material-UI for beautiful components
- Redux Toolkit for efficient state management
- MongoDB for flexible data storage

---

## 📞 Support

For issues or questions, please create an issue in the repository.

---

**Happy Shopping! 🛍️**
