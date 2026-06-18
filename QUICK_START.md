# 🚀 Task Management API - Quick Start Guide

## ✅ Application Status: RUNNING

The Task Management API is now running with H2 in-memory database!

---

## 🌐 Access Points

### 1. **Swagger UI** (Interactive API Documentation)
```
http://localhost:8080/swagger-ui.html
```
- Browse all available endpoints
- Test API calls directly from the browser
- See request/response schemas

### 2. **H2 Database Console** (View Database)
```
http://localhost:8080/h2-console
```
**Connection Details:**
- **JDBC URL:** `jdbc:h2:mem:taskdb`
- **Username:** `sa`
- **Password:** (leave empty)

### 3. **API Documentation (JSON)**
```
http://localhost:8080/api-docs
```

---

## 📝 Quick Test with cURL

### 1. Register a User
```bash
curl -X POST http://localhost:8080/api/auth/register ^
  -H "Content-Type: application/json" ^
  -d "{\"username\":\"testuser\",\"email\":\"test@example.com\",\"password\":\"password123\"}"
```

### 2. Login
```bash
curl -X POST http://localhost:8080/api/auth/login ^
  -H "Content-Type: application/json" ^
  -d "{\"usernameOrEmail\":\"testuser\",\"password\":\"password123\"}"
```

**Save the token from the response!**

### 3. Create a Task
```bash
curl -X POST http://localhost:8080/api/tasks ^
  -H "Content-Type: application/json" ^
  -H "Authorization: Bearer YOUR_TOKEN_HERE" ^
  -d "{\"title\":\"My First Task\",\"description\":\"Testing the API\",\"priority\":\"HIGH\"}"
```

### 4. Get All Tasks
```bash
curl -X GET http://localhost:8080/api/tasks ^
  -H "Authorization: Bearer YOUR_TOKEN_HERE"
```

---

## 🧪 Test with PowerShell

Run the test script:
```powershell
cd task-manager-api
powershell -ExecutionPolicy Bypass -File test-api.ps1
```

---

## 📊 Available Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login and get JWT token

### Tasks (Requires Authentication)
- `GET /api/tasks` - Get all tasks (with optional filters)
- `POST /api/tasks` - Create new task
- `GET /api/tasks/{id}` - Get task by ID
- `PUT /api/tasks/{id}` - Update task
- `DELETE /api/tasks/{id}` - Delete task

### Query Parameters for GET /api/tasks
- `?status=COMPLETED` - Filter by status (TODO, IN_PROGRESS, COMPLETED)
- `?priority=HIGH` - Filter by priority (LOW, MEDIUM, HIGH)
- `?category=Work` - Filter by category
- `?dueDate=2024-12-31` - Filter by due date
- `?search=keyword` - Search in title/description

---

## 🛑 Stop the Application

Press `Ctrl+C` in the terminal where the application is running, or close the PowerShell window.

---

## 📦 Database Information

- **Type:** H2 In-Memory Database
- **Persistence:** Data is stored in memory (lost on restart)
- **Perfect for:** Development and testing
- **Production:** Switch to PostgreSQL/MySQL (see README.md)

---

## ✨ What's Working

✅ User registration and authentication  
✅ JWT token-based security  
✅ Task CRUD operations  
✅ Task filtering and search  
✅ Input validation  
✅ Error handling  
✅ API documentation (Swagger)  
✅ Database console (H2)  

---

## 🎯 Next Steps

1. **Test the API** using Swagger UI or the test script
2. **Explore endpoints** and try different operations
3. **View the database** using H2 Console
4. **Read the full README.md** for detailed documentation

---

**Happy Coding! 🚀**

