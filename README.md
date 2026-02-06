<div align="center">
  <img src="SUSTclubs_logo.png" alt="SUSTclubs Logo" width="200" height="100">
  <h1>SUSTclubs - Club Management System</h1>
  <p><em>A comprehensive university club management platform for SUST</em></p>
</div>

---

## 📋 Table of Contents
- [Overview](#overview)
- [Key Features](#key-features)
- [Technology Stack](#technology-stack)
- [System Architecture](#system-architecture)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Environment Variables](#environment-variables)
- [API Documentation](#api-documentation)
- [Database Models](#database-models)
- [Role-Based Access Control](#role-based-access-control)
- [Development Team](#development-team)

---

## 🎯 Overview

**SUSTclubs** is a full-stack university club management system built for Shahjalal University of Science & Technology (SUST), Sylhet. The platform streamlines club operations with role-based access control, event scheduling, member management, and integrated payment processing. Built with the MERN stack, it provides a scalable and secure solution for managing all aspects of university club activities.

**Key Highlights:**
- ✅ Full-stack MERN application with RESTful API architecture
- ✅ Role-based access control (User, Moderator, Admin)
- ✅ Real-time event scheduling and management
- ✅ Integrated payment gateway (SSLCommerz)
- ✅ Optimized database queries for improved performance
- ✅ Secure authentication with JWT and Google OAuth
- ✅ Responsive admin dashboard and client portal

---

## 🚀 Key Features

### **Club Management**
- Create, edit, and manage multiple university clubs
- Track club members, moderators, and pending applications
- Club logo and website management
- Member approval workflow (pending → approved)

### **Member Management**
- User registration and profile management
- Department and semester tracking (CSE, EEE, CE, ME, BBA, TE, IPE)
- Student ID verification and bio/skills showcase
- Member activity tracking and club association

### **Event Management**
- Create and schedule events with date, time, and location
- Upload event banners and images
- Event association with specific clubs
- Event tracking and modification capabilities

### **Payment Integration**
- SSLCommerz payment gateway integration
- Transaction tracking and order management
- Payment status monitoring (PAID/UNPAID)
- Receipt generation and history

### **Authentication & Security**
- JWT-based authentication with refresh tokens
- Google OAuth 2.0 integration
- Password hashing with bcrypt
- Email verification system
- HTTP-only secure cookies
- Rate limiting on authentication endpoints
- XSS protection and input sanitization

### **Role-Based Access Control**
- **User**: View clubs and basic operations
- **Moderator**: Manage club members, events, and club operations
- **Admin**: Full system access including user management and club creation

### **Communication**
- Automated email notifications (Nodemailer)
- Mass mailing capabilities for club announcements
- Event reminders and notifications

### **Additional Features**
- Multi-language support (i18next) - 16 languages
- File upload system (Cloudinary integration)
- Responsive design with Tailwind CSS
- Dark mode support
- Data export and reporting
- Search and filtering capabilities

---

## 🛠 Technology Stack

### **Backend**
- **Runtime**: Node.js (>= 20.x)
- **Framework**: Express.js
- **Database**: MongoDB with Mongoose ODM
- **Authentication**: Passport.js (JWT & Google OAuth 2.0)
- **Payment Gateway**: SSLCommerz
- **Email Service**: Nodemailer
- **File Storage**: Cloudinary
- **Security**: Helmet, express-xss-sanitizer, express-mongo-sanitize
- **Validation**: Joi
- **Testing**: Jest, Supertest
- **Process Manager**: PM2
- **API Documentation**: Swagger

### **Frontend (Admin Panel)**
- **Framework**: React 19
- **Build Tool**: Vite
- **State Management**: Redux Toolkit
- **Styling**: Tailwind CSS
- **UI Components**: Mantine, Heroicons, Lucide React
- **Charts**: ApexCharts
- **Date Handling**: date-fns
- **Internationalization**: i18next, react-i18next
- **Forms**: React Hook Form
- **Tables**: Mantine DataTable
- **Authentication**: Firebase, JWT Decode

### **Frontend (Client Portal)**
- **Framework**: React 18
- **Build Tool**: Vite
- **State Management**: Redux Toolkit with Redux Persist
- **Styling**: Tailwind CSS
- **UI Library**: Headless UI
- **Icons**: Lucide React, React Icons, Heroicons
- **Animations**: AOS, WOW.js
- **Notifications**: React Toastify, SweetAlert2
- **OAuth**: @react-oauth/google
- **Video**: React Modal Video
- **Image Gallery**: React-18-image-lightbox
- **Carousel**: Swiper

### **Development Tools**
- **Version Control**: Git
- **Code Quality**: Prettier
- **Testing**: Jest
- **API Testing**: Supertest
- **Deployment**: Vercel-ready configuration

---

## 🏗 System Architecture

```
Project350_CMS/
├── Backend/                    # REST API Server
│   ├── src/
│   │   ├── config/            # Configuration files (JWT, Passport, Logger)
│   │   ├── controllers/       # Request handlers
│   │   ├── middlewares/       # Auth, validation, error handling
│   │   ├── models/            # Mongoose schemas (User, Club, Event, Order)
│   │   ├── routes/            # API route definitions
│   │   ├── services/          # Business logic layer
│   │   ├── utils/             # Helper functions
│   │   └── validations/       # Input validation schemas
│   ├── tests/                 # Unit and integration tests
│   └── uploads/               # File upload directory
│
├── admin/                      # Admin Dashboard (React)
│   ├── src/
│   │   ├── components/        # Reusable UI components
│   │   ├── pages/             # Admin pages (Clubs, Events, Members)
│   │   ├── redux/             # State management
│   │   ├── router/            # Route configuration
│   │   └── utils/             # Helper utilities
│   └── public/                # Static assets
│
└── client/                     # Client-facing Portal (React)
    ├── src/
    │   ├── components/        # UI components
    │   ├── pages/             # Public pages
    │   ├── redux/             # State management
    │   └── router/            # Routing logic
    └── public/                # Assets and locales
```

---

## 📦 Prerequisites

Before installation, ensure you have:

- **Node.js** >= 20.x
- **npm** or **yarn** package manager
- **MongoDB** database (local or cloud - MongoDB Atlas)
- **Git** for version control
- **SSLCommerz** merchant account (for payment gateway)
- **Google OAuth 2.0** credentials (optional, for social login)
- **Cloudinary** account (for image uploads)
- **SMTP server** credentials (for email functionality)

---

## ⚙️ Installation

### 1. Clone the Repository
```bash
git clone <repository-url>
cd Project350_CMS
```

### 2. Install Backend Dependencies
```bash
cd Backend
npm install
```

### 3. Install Admin Panel Dependencies
```bash
cd ../admin
npm install
```

### 4. Install Client Portal Dependencies
```bash
cd ../client
npm install
```

### 5. Configure Environment Variables
Create `.env` files in the Backend directory (see [Environment Variables](#environment-variables) section).

### 6. Start MongoDB
Ensure MongoDB is running locally or provide a MongoDB Atlas connection string.

### 7. Run the Application

**Backend (Development):**
```bash
cd Backend
npm run dev
```

**Backend (Production with PM2):**
```bash
npm run prod
```

**Admin Panel:**
```bash
cd admin
npm run dev
```

**Client Portal:**
```bash
cd client
npm run dev
```

---

## 🔐 Environment Variables

Create a `.env` file in the **Backend** directory with the following variables:

```env
# Server Configuration
NODE_ENV=development
PORT=3000

# MongoDB
MONGODB_URL=mongodb://localhost:27017/sustclubs
# Or use MongoDB Atlas:
# MONGODB_URL=mongodb+srv://username:password@cluster.mongodb.net/sustclubs

# JWT Configuration
JWT_SECRET=your_jwt_secret_key_here
JWT_ACCESS_EXPIRATION_MINUTES=30
JWT_REFRESH_EXPIRATION_DAYS=30

# Email Configuration (Nodemailer)
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USERNAME=your_email@gmail.com
SMTP_PASSWORD=your_app_password
EMAIL_FROM=noreply@sustclubs.com

# Google OAuth
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret

# SSLCommerz Payment Gateway
SSLCOMMERZ_STORE_ID=your_store_id
SSLCOMMERZ_STORE_PASSWORD=your_store_password
SSLCOMMERZ_IS_LIVE=false

# Cloudinary (for file uploads)
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

# CORS Origins (comma-separated)
CORS_ORIGIN=http://localhost:5173,http://localhost:5174
```

---

## 📚 API Documentation

The API follows RESTful principles with the following main endpoints:

### **Authentication** (`/v1/auth`)
- `POST /register` - Register new user
- `POST /login` - Login with email/password
- `POST /google` - Google OAuth login
- `POST /logout` - Logout user
- `POST /refresh-tokens` - Refresh access token
- `POST /forgot-password` - Send password reset email
- `POST /reset-password` - Reset password with token

### **Users** (`/v1/users`)
- `GET /` - Get all users (Admin only)
- `GET /:userId` - Get user by ID
- `PATCH /:userId` - Update user
- `DELETE /:userId` - Delete user

### **Clubs** (`/v1/clubs`)
- `POST /` - Create new club (Admin)
- `GET /` - Get all clubs
- `GET /:clubId` - Get club details
- `PATCH /:clubId` - Update club (Moderator/Admin)
- `DELETE /:clubId` - Delete club (Admin)
- `POST /:clubId/join` - Join club (User)
- `POST /:clubId/approve/:userId` - Approve member (Moderator)

### **Events** (`/v1/events`)
- `POST /` - Create event (Moderator/Admin)
- `GET /` - Get all events
- `GET /:eventId` - Get event details
- `PATCH /:eventId` - Update event
- `DELETE /:eventId` - Delete event

### **Payments** (`/v1/sslcommerz`)
- `POST /init` - Initialize payment
- `POST /success` - Payment success callback
- `POST /fail` - Payment failure callback
- `POST /cancel` - Payment cancellation

### **Mail** (`/v1/mail`)
- `POST /send` - Send email
- `POST /bulk` - Send bulk emails

### **Uploads** (`/v1/uploads`)
- `POST /image` - Upload image to Cloudinary
- `GET /events/:filename` - Serve uploaded files

**Swagger Documentation**: Available at `/v1/docs` in development mode.

---

## 🗄 Database Models

### **User Model**
```javascript
{
  name: String (required),
  email: String (required, unique),
  avatar: String (default),
  password: String (required, hashed),
  role: Enum ['user', 'moderator', 'admin'],
  isEmailVerified: Boolean,
  clubs: [ClubId],
  department: Enum ['CSE', 'EEE', 'CE', 'ME', 'BBA', 'TE', 'IPE'],
  semester: Enum ['1.1', '1.2', '2.1', '2.2', '3.1', '3.2', '4.1', '4.2'],
  studentId: String (unique),
  bio: String,
  profession: String,
  skills: Array,
  timestamps: true
}
```

### **Club Model**
```javascript
{
  name: String (required),
  description: String (required),
  logo: String (required),
  website: String,
  moderators: [UserId],
  members: [UserId],
  pendings: [UserId],
  timestamps: true
}
```

### **Event Model**
```javascript
{
  title: String (required),
  description: String (required),
  date: Date (required),
  time: String,
  location: String,
  clubId: ClubId (required),
  createdBy: UserId (required),
  image: String,
  timestamps: true
}
```

### **Order Model**
```javascript
{
  tranId: String (required, unique),
  amount: Number (required),
  currency: String (default: 'BDT'),
  paymentStatus: String (default: 'UNPAID'),
  userName: String (required),
  userEmail: String (required),
  userPhone: String (required),
  userId: UserId,
  clubId: ClubId,
  timestamps: true
}
```

---

## 🔒 Role-Based Access Control

The system implements three-tier role-based access control:

| Role | Permissions |
|------|------------|
| **User** | - View clubs<br>- Join clubs<br>- View events<br>- Make payments<br>- Update own profile |
| **Moderator** | - All user permissions<br>- Manage club members (approve/reject)<br>- Create and manage events<br>- View member details<br>- Send club announcements |
| **Admin** | - All moderator permissions<br>- Create new clubs<br>- Manage all users<br>- Assign moderator roles<br>- Delete clubs<br>- Full system access |

**Implementation:**
- Middleware-based authentication using Passport.js
- JWT tokens with role claims
- Permission checking at route level
- Frontend route protection based on user role

---

## 👥 Development Team

This project was developed as part of the CSE 350 (Software Engineering) course at SUST.

- **Md. Mahfuj Alam** - Registration: 2020331098
- **Latifur Rahman Walid** - Registration: 2020331024
- **Ahasanul Haque Sazid** - Registration: 2020331027

**Institution:** Shahjalal University of Science & Technology, Sylhet, Bangladesh

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](Backend/LICENSE) file for details.

---

## 🙏 Acknowledgments

- SUST Department of Computer Science and Engineering
- All club members and moderators who provided feedback
- Open-source community for the amazing tools and libraries

---

<div align="center">
  <p>Made with ❤️ for SUST Community</p>
  <p>© 2026 SUSTclubs - All Rights Reserved</p>
</div>
