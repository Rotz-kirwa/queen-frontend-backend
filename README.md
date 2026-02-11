# Queen Koba Frontend & Backend

Complete e-commerce solution for Queen Koba skincare products - Frontend and Backend combined.

## 📁 Project Structure

```
queen-frontend-backend/
├── frontend/          # React + Vite customer-facing store
└── backend/           # Flask + MongoDB API
```

## 🚀 Quick Start

### Prerequisites
- Node.js 18+ and npm
- Python 3.8+
- MongoDB

### Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

Frontend runs on: **http://localhost:8080**

### Backend Setup

```bash
cd backend

# Create virtual environment
python3 -m venv venv
source venv/bin/activate

# Install dependencies
pip install flask flask-cors flask-pymongo flask-jwt-extended bcrypt python-dotenv

# Start MongoDB
sudo systemctl start mongodb

# Run backend
python queenkoba_mongodb.py
```

Backend runs on: **http://localhost:5000**

## ✨ Features

### Frontend
- 🛍️ Product catalog with multi-currency support
- 🔐 User authentication (Login/Signup with Google OAuth ready)
- 🛒 Shopping cart
- 💳 Checkout flow
- 📱 Fully responsive design
- 🎨 Luxury UI with Tailwind CSS + shadcn/ui
- 📞 Contact form
- ⭐ Product reviews

### Backend
- 🔒 JWT authentication
- 👤 Customer & admin management
- 📦 Product CRUD operations
- 🛒 Cart management
- 💰 Order processing
- 🎫 Promotions & discounts
- 📊 Admin dashboard APIs

## 🔑 Authentication

### Customer
- **Signup**: POST `/auth/signup` (name, email, phone, password)
- **Login**: POST `/auth/login`

### Admin
- **Login**: POST `/admin/auth/login`
- **Default**: admin@queenkoba.com / admin123

## 📞 Contact

- **Email**: info@queenkoba.com
- **Phone**: 0119 559 180
- **Instagram**: @queenkoba
- **TikTok**: @queenkoba_glow

---

**Built with ❤️ for Queen Koba Skincare**
