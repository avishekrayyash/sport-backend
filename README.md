# 🏟️ SportNest — Backend API

<p align="center">
  A secure RESTful backend API powering the SportNest Sports Facility Booking Management System.
</p>

<p align="center">
  <a href="https://sport-frontend-gray.vercel.app">🌐 Live Website</a>
</p>

---

## 📌 Overview

**SportNest Backend** is a RESTful API built to power the **SportNest Sports Facility Booking Management System**.

The backend manages the core functionality of the platform, including:

* User authentication
* User authorization
* Sports facility management
* Facility CRUD operations
* Booking management
* User-specific reservations
* JWT-based protected APIs
* MongoDB data management
* Secure frontend-backend communication

The API is designed to provide a reliable and secure backend layer for the SportNest frontend application.

---

## 🌐 Live Project

### Frontend

🔗 https://sport-frontend-gray.vercel.app

### Backend API

🔗 Add your deployed backend API URL here

---

# ✨ Core Features

## 🔐 Authentication

SportNest uses **Better Auth** to provide secure user authentication.

### Supported Authentication

* Email & Password authentication
* Google Sign-In
* Secure session management
* User authentication
* Protected resources
* Authentication-based API access

---

# 🛡️ JWT Authorization

The backend uses **JSON Web Tokens (JWT)** to protect private API routes.

Authenticated users receive authorization that allows them to access protected resources.

### Protected Operations

* Creating facilities
* Updating facilities
* Deleting facilities
* Creating bookings
* Managing user-specific bookings
* Accessing protected resources

### Authorization Flow

```text
User
 │
 ▼
Login / Google Sign-In
 │
 ▼
Better Auth
 │
 ▼
Authenticated User
 │
 ▼
JWT Token
 │
 ▼
Protected API Request
 │
 ▼
JWT Verification
 │
 ▼
Authorized Request
```

---

# 🏟️ Facility Management API

The backend provides complete CRUD functionality for sports facilities.

## Create Facility

Authorized users can create new sports facility listings.

```text
POST /facilities
```

Example data:

```json
{
  "name": "Green Field Sports Complex",
  "location": "Sylhet",
  "category": "Football",
  "price": 1500,
  "description": "Modern football facility",
  "image": "facility-image-url"
}
```

---

## Get Facilities

Users can retrieve available sports facilities.

```text
GET /facilities
```

---

## Get Facility Details

Retrieve information about a specific facility.

```text
GET /facilities/:id
```

---

## Update Facility

Authorized users can update their facility information.

```text
PUT /facilities/:id
```

---

## Delete Facility

Authorized users can remove their facility listings.

```text
DELETE /facilities/:id
```

---

# 📅 Booking Management API

The backend provides APIs for managing sports facility reservations.

### Booking Features

* Create booking
* View bookings
* View user bookings
* Manage reservations
* Update booking information
* Cancel bookings
* Check facility availability
* Store booking information

---

## Create Booking

```text
POST /bookings
```

Example:

```json
{
  "facilityId": "facility_id",
  "userId": "user_id",
  "date": "2026-10-20",
  "time": "18:00",
  "duration": 2
}
```

---

## Get Bookings

```text
GET /bookings
```

---

## Get User Bookings

```text
GET /bookings/user/:userId
```

---

## Update Booking

```text
PUT /bookings/:id
```

---

## Delete / Cancel Booking

```text
DELETE /bookings/:id
```

> Endpoint names may vary depending on the final backend implementation.

---

# 🔄 Facility Management Flow

```text
User
 │
 ▼
Authenticate
 │
 ▼
Access Facility Management
 │
 ├──────────────┐
 │              │
 ▼              ▼
Create         View
 │              │
 ▼              ▼
Update         Details
 │
 ▼
Delete
```

---

# 📅 Booking Flow

```text
User
 │
 ▼
Browse Facilities
 │
 ▼
Select Facility
 │
 ▼
Check Availability
 │
 ▼
Select Date & Time
 │
 ▼
Create Booking
 │
 ▼
Booking Stored
 │
 ▼
Manage Reservation
```

---

# 🗄️ Database

SportNest uses **MongoDB** for efficient and scalable data storage.

The database can contain collections such as:

```text
SportNest Database
│
├── Users
│
├── Facilities
│
└── Bookings
```

### Users

Stores authentication and user-related information.

```text
User
├── Name
├── Email
├── Profile Information
└── Authentication Data
```

### Facilities

Stores sports facility information.

```text
Facility
├── Name
├── Description
├── Category
├── Location
├── Price
├── Image
├── Owner
└── Availability
```

### Bookings

Stores reservation information.

```text
Booking
├── User
├── Facility
├── Date
├── Time
├── Duration
└── Status
```

---

# 🛠️ Technology Stack

## Runtime & Framework

* **Node.js** — JavaScript runtime
* **Express.js** — REST API framework

## Database

* **MongoDB**
* **MongoDB Atlas**

## Authentication

* **Better Auth**
* **MongoDB Adapter**

## Authorization

* **JWT (JSON Web Token)**

## Middleware & Configuration

* **CORS**
* **Dotenv**

---

# 📦 NPM Packages

Main backend packages include:

```text
express
mongodb
jsonwebtoken
cors
dotenv
better-auth
@better-auth/mongodb-adapter
```

Development dependencies may include:

```text
nodemon
```

> The package list should be kept synchronized with the project's actual `package.json`.

---

# 🏗️ Backend Architecture

SportNest follows a client-server architecture where the Next.js frontend communicates with the backend through REST APIs.

```text
┌──────────────────────────┐
│      SportNest Frontend  │
│       Next.js + React    │
└────────────┬─────────────┘
             │
             │ HTTP / REST API
             ▼
┌──────────────────────────┐
│      SportNest Backend   │
│     Node.js + Express    │
└────────────┬─────────────┘
             │
       ┌─────┴─────┐
       │           │
       ▼           ▼
┌────────────┐ ┌────────────┐
│  MongoDB   │ │ Better Auth│
│  Database  │ │   / JWT    │
└────────────┘ └────────────┘
```

---

# 🔄 API Request Architecture

```text
Client
  │
  ▼
HTTP Request
  │
  ▼
Express Server
  │
  ▼
CORS Middleware
  │
  ▼
Authentication
  │
  ▼
JWT Verification
  │
  ▼
Route Handler
  │
  ▼
Database Operation
  │
  ▼
MongoDB
  │
  ▼
JSON Response
  │
  ▼
Client
```

---

# 🔒 Security

Security is an important part of the SportNest backend.

### Security Measures

* JWT-based authorization
* Protected API routes
* Better Auth authentication
* Secure session management
* MongoDB secure connection
* CORS configuration
* Environment variables
* Authentication middleware
* Protected CRUD operations
* User-specific booking access

Sensitive credentials should never be committed to GitHub.

---

# 🌍 Environment Variables

Create a `.env` file in the backend root directory.

```env
PORT=5000

MONGODB_URI=your_mongodb_connection_string

BETTER_AUTH_SECRET=your_better_auth_secret

JWT_SECRET=your_jwt_secret

CLIENT_URL=https://sport-frontend-gray.vercel.app
```

> Use the exact environment variable names required by your actual implementation.

---

# 🚀 Getting Started

## 1. Clone the Repository

```bash
git clone https://github.com/your-username/sportnest-backend.git
```

## 2. Navigate to the Backend

```bash
cd sportnest-backend
```

## 3. Install Dependencies

```bash
npm install
```

## 4. Configure Environment Variables

Create a `.env` file:

```env
MONGODB_URI=your_mongodb_uri
BETTER_AUTH_SECRET=your_secret
JWT_SECRET=your_jwt_secret
CLIENT_URL=http://localhost:3000
```

## 5. Start the Development Server

```bash
npm run dev
```

The backend will run at:

```text
http://localhost:5000
```

---

# 📜 Available Scripts

### Development

```bash
npm run dev
```

Starts the development server using Nodemon.

### Production

```bash
npm start
```

Starts the backend in production mode.

---

# 📡 API Modules

| Module            | Functionality                                    |
| ----------------- | ------------------------------------------------ |
| 🔐 Authentication | Register, login, Google authentication, sessions |
| 👤 Users          | User information and authentication              |
| 🏟️ Facilities    | Create, read, update, delete facilities          |
| 📅 Bookings       | Create and manage reservations                   |
| 🛡️ Authorization | JWT-based protected routes                       |
| 🗄️ Database      | MongoDB data management                          |

---

# 📊 Example API Response

A successful response can follow a structure such as:

```json
{
  "success": true,
  "message": "Request successful",
  "data": {}
}
```

An error response:

```json
{
  "success": false,
  "message": "Something went wrong"
}
```

> Adjust these examples to match the actual API response structure.

---

# 📁 Suggested Project Structure

```text
sportnest-backend/
│
├── config/
│   └── db.js
│
├── middleware/
│   ├── auth.js
│   └── verifyToken.js
│
├── routes/
│   ├── auth.routes.js
│   ├── facility.routes.js
│   ├── booking.routes.js
│   └── user.routes.js
│
├── controllers/
│   ├── facility.controller.js
│   ├── booking.controller.js
│   └── user.controller.js
│
├── services/
│   └── ...
│
├── server.js
├── package.json
├── .env
└── README.md
```

> This is a representative structure. Update it according to your actual repository structure.

---

# 🎯 Project Objectives

The main objectives of the SportNest backend are to:

1. Provide a reliable RESTful API for the sports facility platform.
2. Securely authenticate and authorize users.
3. Implement complete facility CRUD operations.
4. Provide an efficient booking management system.
5. Store application data securely using MongoDB.
6. Protect private APIs using JWT authorization.
7. Provide a clean backend architecture for frontend integration.
8. Create a scalable foundation for future marketplace and booking features.

---

# 🔮 Future Improvements

Potential backend improvements include:

* 💳 Online payment integration
* ⭐ Facility reviews and ratings
* 📍 Location-based facility search
* 🔎 Advanced search and filtering
* 📅 Calendar-based availability management
* 🔔 Real-time booking notifications
* 💬 User-facility owner messaging
* 📊 Advanced facility analytics
* 🧪 Automated API testing
* 📖 Swagger/OpenAPI documentation
* ⚡ API caching
* 🛡️ Rate limiting
* 📈 Performance monitoring

---

# 👨‍💻 Author

## Avishek Roy Yash

**Full Stack Developer | Aspiring Software Engineer**

📧 Email: `avishekrayyash@gmail.com`

🔗 GitHub: `https://github.com/avishekrayyash`

🔗 LinkedIn: `https://linkedin.com/in/avishek-ray-yash`

---

# ⭐ Support

If you find **SportNest** useful or interesting, consider giving the repository a ⭐ **Star** on GitHub.

Your support and feedback are greatly appreciated!

---

# 📄 License

This project was developed for **educational and portfolio purposes**.

© 2026 **Avishek Ray Yash**. All rights reserved.
