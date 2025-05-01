🧾 Employee Management CRUD Application (Spring Boot + Angular)
📌 Description
A full-stack web application that allows HR to manage employee records with basic CRUD operations. Built using:

Backend: Spring Boot (REST API, JPA, H2/MySQL)

Frontend: Angular

Upcoming Feature: Login/logout (only HR can access CRUD)

✅ Features Implemented
🔧 Backend – Spring Boot
GET /employees – Fetch all employees

GET /employees/{id} – Fetch employee by ID

POST /employees – Create a new employee

PUT /employees/{id} – Update existing employee

DELETE /employees/{id} – Delete employee by ID

All operations return appropriate ResponseEntity objects and use a custom exception:

java
Copy
Edit
throw new ResourceNotFoundException("Employee not found with id: " + id);

---------------------------------------------------------------------------------------------
💻 Frontend – Angular
Employee List Table using *ngFor

Add Employee Form using [(ngModel)]

Update and Delete actions per row

Integrated with backend using HttpClient

Basic Bootstrap styling

🔐 Planned Feature: Login & Authorization (Coming Soon)
We plan to implement secure login so that only HR can perform CRUD.

📘 Theoretical Plan
1) Spring Boot (Backend):
Add Spring Security & JWT dependencies

Create /login endpoint

Restrict all /employees/** endpoints to authenticated users (HR only)

Use User model with username/password/role

Return JWT token on successful login

2) Angular (Frontend):
Create Login Page

Store token in localStorage

Create AuthGuard to protect routes

Add HTTP Interceptor to attach JWT in every request

Implement Logout by clearing token and redirecting to login page

💡 How to Run the Project
📦 Backend – Spring Boot
bash
Copy
Edit
cd backend
./mvnw spring-boot:run
🌐 Frontend – Angular
bash
Copy
Edit
cd frontend
npm install
ng serve
📂 Folder Structure
swift
Copy
Edit
project-root/
│
├── backend/
│   └── src/main/java/com/example/employees/
│       ├── controller/
│       ├── service/
│       ├── model/
│       └── exception/
│
├── frontend/
│   ├── src/app/
│   │   ├── employee-list/
│   │   ├── create-employee/
│   │   └── services/