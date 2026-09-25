# Smart Complaint & Service Management Platform

A full-stack microservice-based complaint and service management platform built using Java, Spring Boot, ReactJS, MySQL, JWT, and OAuth2.

## Project Overview

The Smart Complaint & Service Management Platform allows customers to raise and track complaints, employees to manage assigned complaints, managers to assign and monitor complaints, and administrators to manage users and system operations.

## Features

- Customer registration and login
- JWT-based authentication and authorization
- Google OAuth2 authentication
- Role-based access control
- Customer complaint creation and tracking
- Employee complaint assignment and status updates
- Manager complaint assignment and monitoring
- Admin user management
- Complaint priority and SLA management
- Complaint history tracking
- Search, filtering, sorting, and pagination
- RESTful APIs
- Microservice architecture

## User Roles

### Customer

- Register and login
- Create complaints
- View complaints
- Track complaint status
- View complaint history

### Employee

- View assigned complaints
- Update complaint status
- Manage assigned service requests

### Manager

- View complaints
- Assign complaints to employees
- Monitor complaint status

### Admin

- View users
- Create employees
- Create managers
- Update users
- Delete users

## Technology Stack

### Backend

- Java
- Spring Boot
- Spring MVC
- Spring Data JPA
- Hibernate
- Spring Security
- JWT
- OAuth2
- OpenFeign
- REST APIs

### Frontend

- ReactJS
- JavaScript
- HTML5
- CSS3
- Tailwind CSS

### Database

- MySQL

### Microservices

- Eureka Server
- API Gateway
- User Service
- Complaint Service
- Assignment Service

### Tools

- Maven
- Postman
- Git
- GitHub
- Docker

## System Architecture

```text
                    ReactJS Frontend
                           |
                           v
                     API Gateway
                        :8080
                           |
                           v
                    Eureka Server
                        :8761
                           |
          +----------------+----------------+
          |                |                |
          v                v                v
     User Service    Complaint Service  Assignment Service
        :8081              :8082              :8083
          |                  |                  |
          v                  v                  |
       MySQL               MySQL             OpenFeign
                                                |
                                                v
                                        Complaint Service
```

## Repository Links

| Component | Repository |
|---|---|
| Main Project | [SmartComplaint-Management-System](https://github.com/Arifunisha/SmartComplaint-Management-System) |
| Frontend | [SmartComplaint-Frontend](https://github.com/Arifunisha/SmartComplaint-Frontend) |
| User Service | [SmartComplaint-UserService](https://github.com/Arifunisha/SmartComplaint-UserService) |
| Complaint Service | [SmartComplaint-ComplaintService](https://github.com/Arifunisha/SmartComplaint-ComplaintService) |
| Assignment Service | [SmartComplaint-AssignmentService](https://github.com/Arifunisha/SmartComplaint-AssignmentService) |
| API Gateway | [SmartComplaint-ApiGateway](https://github.com/Arifunisha/SmartComplaint-ApiGateway) |
| Eureka Server | [SmartComplaint-EurekaServer](https://github.com/Arifunisha/SmartComplaint-EurekaServer) |

## Authentication

The application supports two authentication methods.

### Email and Password Authentication

```text
Email + Password
       |
       v
     BCrypt
       |
       v
     Login
       |
       v
      JWT
       |
       v
 Protected APIs
```

### Google OAuth2 Authentication

```text
Google Login
     |
     v
Google Authentication
     |
     v
Create / Find Customer
     |
     v
Generate JWT
     |
     v
React Frontend
```

## API Gateway

All frontend API requests are routed through the API Gateway.

```text
/users/**        -> User Service
/complaints/**   -> Complaint Service
/assignments/**  -> Assignment Service
```

## Database

```text
User Service       -> user_db
Complaint Service  -> complaint_db
```

## Application Ports

| Component | Port |
|---|---:|
| React Frontend | 5173 |
| API Gateway | 8080 |
| User Service | 8081 |
| Complaint Service | 8082 |
| Assignment Service | 8083 |
| Eureka Server | 8761 |

## API Testing

REST APIs were tested using Postman, including:

- Authentication
- User management
- Complaint management
- Complaint assignment
- Status updates
- Authorization
- Validation
- Error handling

## How to Run

Start the services in the following order:

```text
1. MySQL
2. Eureka Server
3. User Service
4. Complaint Service
5. Assignment Service
6. API Gateway
7. React Frontend
```

### Backend

Each backend service can be started using Maven:

```bash
mvn spring-boot:run
```

### Frontend

Navigate to the frontend repository and run:

```bash
npm install
npm run dev
```

## Environment Variables

Sensitive credentials are stored using environment variables and are not committed to GitHub.

Example:

```properties
DB_USERNAME=your_username
DB_PASSWORD=your_password
JWT_SECRET=your_jwt_secret
GOOGLE_CLIENT_ID=your_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
```

## Project Status

The project includes:

- Microservice backend
- Service discovery using Eureka
- API Gateway
- JWT authentication
- Google OAuth2 authentication
- Role-based authorization
- Complaint management
- Employee assignment
- React frontend
- REST API testing

## Author

**Arifunisha**

B.Tech Computer Science & Engineering