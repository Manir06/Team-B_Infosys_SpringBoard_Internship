# Inventra - Intelligent Inventory Management System

A full-stack inventory management system with JWT-based authentication and role-based access control.

## 🚀 Features

### Authentication & Authorization
- ✅ JWT-based authentication
- ✅ Role-based access control (ADMIN, MANAGER, STAFF)
- ✅ Secure password encryption with BCrypt
- ✅ Protected routes on frontend and backend

### User Management (Admin Only)
- ✅ Create, Read, Update, Delete users
- ✅ Toggle user status (enable/disable)
- ✅ Filter users by role
- ✅ Search users by name, username, or email

### Tech Stack

#### Backend
- Java 17
- Spring Boot 3.2.1
- Spring Security
- Spring Data JPA
- MySQL Database
- JWT (JSON Web Tokens)
- Maven

#### Frontend
- React 18
- TypeScript
- Tailwind CSS
- React Router v6
- Axios
- Vite

## 📋 Prerequisites

- Java 17 or higher
- Maven 3.6+
- Node.js 18+ and npm
- MySQL 8.0+

## 🛠️ Setup Instructions

### Backend Setup

1. **Navigate to backend directory:**
   ```bash
   cd Inventra_Intelligent_Inventory_Management_System_Backend
   ```

2. **Configure MySQL Database:**
   - Create a MySQL database named `inventra_db` (or it will be auto-created)
   - Update `src/main/resources/application.properties` if needed:
     ```properties
     spring.datasource.url=jdbc:mysql://localhost:3306/inventra_db
     spring.datasource.username=root
     spring.datasource.password=root
     ```

3. **Build and Run:**
   ```bash
   mvn clean install
   mvn spring-boot:run
   ```

   The backend will start on `http://localhost:8080`

### Frontend Setup

1. **Navigate to frontend directory:**
   ```bash
   cd Inventra_Intelligent_Inventory_Management_System_Frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start development server:**
   ```bash
   npm run dev
   ```

   The frontend will start on `http://localhost:5173`

## 🔐 Default User Credentials

The system creates three default users on first startup:

| Role    | Username | Password    | Email                |
|---------|----------|-------------|----------------------|
| ADMIN   | admin    | admin123    | admin@inventra.com   |
| MANAGER | manager  | manager123  | manager@inventra.com |
| STAFF   | staff    | staff123    | staff@inventra.com   |

## 🎯 API Endpoints

### Authentication Endpoints (Public)
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user (requires JWT)

### Admin Endpoints (ADMIN role only)
- `GET /api/admin/users` - Get all users
- `GET /api/admin/users/role/{role}` - Get users by role
- `POST /api/admin/users` - Create new user
- `PUT /api/admin/users/{id}` - Update user
- `DELETE /api/admin/users/{id}` - Delete user
- `PATCH /api/admin/users/{id}/toggle-status` - Toggle user status

### Manager Endpoints (ADMIN, MANAGER)
- `GET /api/manager/dashboard` - Manager dashboard

### Staff Endpoints (All authenticated users)
- `GET /api/staff/dashboard` - Staff dashboard

## 🎨 Frontend Routes

- `/login` - Login page
- `/register` - Registration page
- `/dashboard` - Main dashboard (protected)
- `/admin/users` - User management (ADMIN only)
- `/unauthorized` - Access denied page

## 🔒 Security Features

1. **JWT Authentication**: Stateless authentication using JSON Web Tokens
2. **Password Encryption**: BCrypt hashing for secure password storage
3. **Role-Based Access Control**: Three-tier permission system
4. **CORS Configuration**: Configured for local development
5. **Request Validation**: Input validation on both frontend and backend
6. **Protected Routes**: Frontend route guards and backend endpoint security

## 📁 Project Structure

### Backend
```
src/main/java/com/inventra/inventory/
├── config/          # Configuration classes
├── controller/      # REST controllers
├── dto/            # Data Transfer Objects
├── exception/      # Exception handlers
├── model/          # Entity classes
├── repository/     # JPA repositories
├── security/       # Security configuration
└── service/        # Business logic
```

### Frontend
```
src/
├── components/     # Reusable components
├── context/        # React Context (Auth)
├── pages/          # Page components
├── services/       # API services
├── types/          # TypeScript types
└── App.tsx         # Main app component
```

## 🚀 Building for Production

### Backend
```bash
mvn clean package
java -jar target/inventory-management-system-1.0.0.jar
```

### Frontend
```bash
npm run build
```

The production build will be in the `dist/` directory.

## 📝 License

This project is created for educational purposes.

## 👨‍💻 Author

Created as part of the Inventra Intelligent Inventory Management System project.
