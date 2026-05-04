# 🚀 PrepX Backend

A Spring Boot backend application that provides **OTP-based authentication**, **JWT security**, **question management**, and **user progress tracking**.

---

## 📌 Project Overview

PrepX Backend is designed to handle:

- 🔐 User Authentication using OTP & JWT  
- 📩 Email OTP verification  
- 📚 Question management (CSV upload supported)  
- 📊 User progress tracking  
- 🛡️ Secure REST APIs  

---

## 🏗️ Architecture

The project follows a **layered architecture**:



### Layers:

- **Controller Layer**
  - Handles API requests
  - Uses `@RestController`

- **Service Layer**
  - Contains business logic
  - Uses `@Service`

- **Repository Layer**
  - Handles database operations
  - Uses Spring Data JPA

- **Model Layer**
  - Represents database entities

---

## 🧩 Models Used

### 👤 User
- Stores user details
- Fields: `id`, `fullName`, `email`, `password`
- Used for authentication & JWT

### ❓ Question
- Stores MCQ questions
- Fields:
  - `category`
  - `difficulty`
  - `questionText`
  - `options`
  - `correctAnswer`

### 📊 Progress
- Tracks user performance
- Fields:
  - `user`
  - `score`
  - `category`
  - `difficulty`
  - `date`

---

## ⚙️ Key Features

### 🔐 Authentication
- Signup & Login
- Password encryption using BCrypt
- JWT Token generation & validation

### 📩 OTP Verification
- Email-based OTP system
- Secure login flow

### 📚 Question Management
- Upload questions using CSV
- Fetch questions by category & difficulty

### 📊 Progress Tracking
- Save user test results
- Retrieve user history

---

## 🔑 Technologies Used

- Java
- Spring Boot
- Spring Security
- Spring Data JPA
- JWT (io.jsonwebtoken)
- MySQL / PostgreSQL
- JavaMailSender
- Maven

---

## 🔒 Security Flow

1. User registers / logs in  
2. OTP is sent via email  
3. OTP is verified  
4. JWT token is generated  
5. Token is used for protected API access  

---

## 📡 API Endpoints (Sample)

### Auth APIs
- `POST /auth/signup`
- `POST /auth/signing`
- `POST /auth/send-otp`
- `POST /auth/verify-otp`

### Question APIs
- `GET /api/questions?category=&difficulty=`
- `GET /api/questions/all`

### Progress APIs
- `POST /api/progress/save`
- `GET /api/progress/{userId}`

---

## 🛠️ Configuration

Update your `application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/prepex
spring.datasource.username=root
spring.datasource.password=your_password

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

spring.mail.host=smtp.gmail.com
spring.mail.port=587
spring.mail.username=your_email
spring.mail.password=your_app_password
spring.mail.properties.mail.smtp.auth=true
spring.mail.properties.mail.smtp.starttls.enable=true


Structure:-
com.prepXBackend
 ├── config
 ├── controller
 ├── model
 ├── repository
 ├── request
 ├── response
 ├── service
 └── helper
