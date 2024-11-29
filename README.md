# **Role-Based Access Control (RBAC) with Authentication and Authorization**

This project is an advanced implementation of **Role-Based Access Control (RBAC)** with secure authentication and authorization mechanisms. It includes features like user registration, login, logout, and access control based on roles such as Admin, User, and Moderator. The system also includes support for email verification, login history tracking, and password management.

The application adheres to secure coding practices and is built using **Node.js**, **Express.js**, **MongoDB**, and **Passport.js**. It also includes WebSocket support for real-time updates and a modular architecture for scalability.

---

## **Table of Contents**

- [Features](#features)
- [Architecture and Directory Structure](#architecture-and-directory-structure)
- [Setup and Running the Application](#setup-and-running-the-application)
- [API Documentation](#api-documentation)
- [Endpoints](#endpoints)
- [Role-Based Access Control (RBAC)](#role-based-access-control-rbac)
- [Built With](#built-with)
- [Contributing](#contributing)

---

## **Features**

### Authentication and Authorization
- User registration and email verification.
- Login with credentials and OTP support.
- Role-based access control using middleware.
- Password management, including password change functionality.

### Session and Login Management
- JSON Web Token (JWT) for secure session handling.
- Track login history with device details.
- Manage logged-in devices for each user.
- Real-time logout and login updates using WebSockets.

### Security
- Password hashing using `bcrypt`.
- Prevent unauthorized access with middleware.
- Email notifications for new device logins.

### API Documentation
- Interactive Swagger documentation for seamless API testing and integration.

---

## **Architecture and Directory Structure**

This project is modularized and scalable, designed with separation of concerns.

```bash
RBAC-Auth-System/
├── routes/                   # API route definitions
│   ├── authRoutes.ts         # Authentication routes
│   ├── userRoutes.ts         # User management routes
├── controllers/              # Request handlers
│   ├── authController.ts     # Handles authentication logic
│   ├── userController.ts     # Handles user logic
├── models/                   # Database schemas
│   ├── userSchema.ts         # User schema
│   ├── loginHistorySchema.ts # Login history schema
│   ├── tokenSchema.ts        # Verification token schema
├── util/                     # Utility functions
│   ├── utils.ts              # Helper functions
│   ├── sendEmail.ts          # Email sender logic
├── middleware/               # Middleware
│   ├── errorHandler.ts       # Error handling middleware
├── config/                   # Configuration files
├── database/                 # Database connection logic
├── public/                   # Static assets
└── app.ts                    # Main application entry point
```

---

## **Login Page**

Users can log in to their accounts using credentials or OTP. Below is an example of the login interface:

![Login Page](./docs/assets/Screenshot%202024-05-06%20121439.png)

---

## **Admin Panel**

Admins can view and manage all user details, including device and authentication history. Here’s a preview of the admin panel interface:

![Admin Panel](./docs/assets/Screenshot%202024-05-06%20132822.png)

---

## **Setup and Running the Application**

### Prerequisites
- **Node.js** and **npm** installed.
- MongoDB database instance (local or cloud).

### Steps to Run
1. **Clone the repository**:
   ```bash
   git clone <repository_url>
   cd RBAC-Auth-System
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Set up environment variables**:
   - Create `.env` files in `apps/web` and `apps/server` directories as described in the code.

4. **Start the application**:
   ```bash
   npm run dev
   ```

5. **Docker Support**:
   - Build and run the backend API using Docker (optional).

---

## **API Documentation**

Access the interactive Swagger documentation:
```bash
http://localhost:<PORT>/api-docs
```

---

## **Endpoints**

### Authentication Routes
| Method | Endpoint                  | Description                   |
|--------|---------------------------|-------------------------------|
| POST   | `/api/v0.1/auth/login`    | Login with credentials.       |
| POST   | `/api/v0.1/auth/register` | Register a new user.          |
| GET    | `/api/v0.1/auth/verify-email/:id` | Verify email address. |
| POST   | `/api/v0.1/auth/verify-login/:id` | Verify login OTP.       |
| GET    | `/api/v0.1/auth/login-history/:userId` | Fetch login history.|
| POST   | `/api/v0.1/auth/logout/:userId` | Logout from a device.    |
| POST   | `/api/v0.1/auth/change-password/:userId` | Change password.    |

### User Routes
| Method | Endpoint               | Description                  |
|--------|-------------------------|------------------------------|
| GET    | `/api/v0.1/users/`      | Fetch all users.             |
| GET    | `/api/v0.1/users/:userId` | Fetch user by ID.           |

---

## **Role-Based Access Control (RBAC)**

- **Admin**: Full access to all functionalities.
- **Moderator**: Limited admin privileges.
- **User**: Access to personal account management.

---

## **Built With**

- **Node.js**: Backend runtime.
- **Express.js**: Web framework.
- **MongoDB**: NoSQL database.
- **WebSocket**: Real-time updates.
- **bcrypt**: Password hashing.
- **Nodemailer**: Email functionality.

---

## **Contributing**

Contributions are welcome. Here's how to contribute:
1. Fork the repository.
2. Make your changes.
3. Create a pull request with a description.
