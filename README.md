
# 🗂️ Task Management System

A Task Management System for planning, tracking, and managing software projects. The platform enables teams to create projects, manage boards and sprints, track issues, assign tasks, link related work, and monitor workflows through a modern web interface.

![Java](https://img.shields.io/badge/Java-17+-007396?style=for-the-badge&logo=java&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.x-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)
![React](https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![MySQL](https://img.shields.io/badge/MySQL-8+-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-Authentication-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)

---

## 📋 Table of Contents
- Features  
- Tech Stack  
- Prerequisites  
- Installation  
- Configuration  
- Running the Application  
- Project Structure  
- Usage Guide  
- API Documentation
- Screenshots  
  

## ✨ Features

### 🔐 **Authentication & Authorization**
- JWT-based secure authentication with refresh tokens
- Role-based access control (Admin, Project Manager, Developer)
- Password encryption using BCrypt
- Session management

### 📊 **Project Management**
- Create and manage multiple projects
- Team member assignment and role management
- Project-specific configurations
- Progress tracking and metrics

### 🎯 **Task & Issue Tracking**
- Create, update, and assign tasks and issues
- Custom workflow status management
- Priority levels (Critical, High, Medium, Low)
- Task dependencies and linking
- File attachments and comments

### 📈 **Workflow & Boards**
- Customizable workflow states
- Interactive Kanban boards
- Drag-and-drop card management
- Status transition tracking

### 🔔 **Collaboration Tools**
- Real-time notifications
- Team assignment and mentions
- Activity tracking
- Comment threads and discussions

### 📱 **Dashboard & Analytics**
- Interactive dashboards
- Sprint progress tracking
- Performance metrics
- Visual data representation

---

## 🛠️ Tech Stack

### Backend
- **Java 17+** - Core programming language
- **Spring Boot 3.x** - Framework for Java applications
- **Spring Security** - Authentication and authorization
- **Spring Data JPA** - Database operations
- **MySQL** - Relational database
- **JWT** - JSON Web Token for authentication
- **Maven** - Dependency management

### Frontend
- **React 18+** - JavaScript library for UI
- **Axios** - HTTP client for API calls
- **React Router** - Navigation and routing
- **Tailwind CSS** - Utility-first CSS framework

### Tools & DevOps
- **Postman** - API testing
- **Git** - Version control


---

## 📦 Prerequisites

Before you begin, ensure you have the following installed on your system:

### Required Software
- **Java 17+** - [Download Java](https://www.oracle.com/java/technologies/downloads/)
- **Node.js 18+** - [Download Node.js](https://nodejs.org/)
- **MySQL 8+** - [Download MySQL](https://dev.mysql.com/downloads/)
- **Git** - [Download Git](https://git-scm.com/)
- **Maven 3.8+** - [Download Maven](https://maven.apache.org/download.cgi)

### Check Your Installations
```
# Check Java version
java --version

# Check Node.js version
node --version

# Check npm version
npm --version

# Check MySQL version
mysql --version

# Check Maven version
mvn --version
```
## 🚀 Installation
### Step 1: Clone the Repository
```git clone https://github.com/yourusername/task-management-system.git
cd task-management-system
```
### Step 2: Backend Setup
``` cd backend
mvn clean install
```
### Step 3: Frontend Setup
### 3.1 Navigate to Frontend Directory
```
cd frontend
```
### 3.2 Install Node Dependencies
```
npm install
```
### Step 4: MySQL Setup
#### 4.1 Start MySQL Service
```
# Windows
net start MySQL

# macOS
brew services start mysql

# Linux
sudo systemctl start mysql
```
### 4.2 Verify MySQL is Running
```
mysql --version
```
## ⚙️ Configuration
### Backend Configuration
Create an application.properties file in:
```
cd backend/src/main/resources
```
Edit application.properties with the following content:

```
# MySQL Configuration
spring.datasource.url=jdbc:mysql://localhost:3306/task_db
spring.datasource.username=root
spring.datasource.password=yourpassword

# JPA / Hibernate Configuration
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect

# JWT Configuration
jwt.secret=your-super-secret-jwt-key
jwt.expiration=86400000
```
### Frontend Configuration
Create a .env file in the frontend/ directory:
```
cd frontend
```
Create frontend/.env file with the following content:
# API Base URL
VITE_API_BASE_URL=http://localhost:8080

## 🏃 Running the Application
### Step 1: Start MySQL

Make sure MySQL service is running (see MySQL Setup section)
### Step 2: Start Backend Server
```# Navigate to backend directory
cd backend

# Start Spring Boot application    
mvn spring-boot: run
Backend will be available at:
http://localhost:8080
```
### Step 3: Start Frontend Development Server
Open a new terminal and run:
```
# Navigate to frontend directory
cd frontend

# Start React development server
npm start
```
Frontend will be available at:
http://localhost:3000 

## 📁 Project Structure
```
task-management-system/
├── 📁 backend/
│ ├── 📁 src/main/java/com/TaskManagement/
│ │ ├── 📁 Client/ # 🚀 External Service Clients
│ │ │ ├── IssueClient.java
│ │ │ └── UserClient.java
│ │ │
│ │ ├── 📁 Config/ # ⚙️ Configuration Classes
│ │ │
│ │ ├── 📁 Controller/ # 🌐 REST API Controllers
│ │ │ ├── AttachmentController.java # 📎 File Upload/Download
│ │ │ ├── BackLogController.java # 📋 Backlog Management
│ │ │ ├── BoardController.java # 🎯 Board Operations
│ │ │ ├── BoardCardController.java # 🃏 Card Management
│ │ │ ├── FileDownloadController.java # ⬇️ File Serving
│ │ │ ├── IssueController.java # 🐛 Issue Handling
│ │ │ ├── IssueLinkController.java # 🔗 Issue Linking
│ │ │ ├── NotificationController.java # 🔔 Real-time Notifications
│ │ │ ├── SprintController.java # 🏃 Sprint Planning
│ │ │ ├── TaskController.java # ✅ Task Operations
│ │ │ ├── UserAuthenticationController.java # 🔐 Auth Endpoints
│ │ │ ├── UserController.java # 👤 User Management
│ │ │ └── WorkFlowController.java # 📊 Workflow Configuration
│ │ │
│ │ ├── 📁 DTO/ # 📦 Data Transfer Objects
│ │ │ ├── LoginRequestDTO.java # 👤 Login Request
│ │ │ ├── RegisterRequestDTO.java # 📝 Registration Data
│ │ │ ├── TaskDTO.java # ✅ Task Data Transfer
│ │ │ ├── IssueDTO.java # 🐛 Issue Data Transfer
│ │ │ └── WorkFlowDTO.java # 📊 Workflow Data
│ │ │
│ │ ├── 📁 Entity/ # 🗃️ Database Entities
│ │ │ ├── User.java # 👤 User Entity
│ │ │ ├── Task.java # ✅ Task Entity
│ │ │ ├── Issue.java # 🐛 Issue Entity
│ │ │ ├── Sprint.java # 🏃 Sprint Entity
│ │ │ └── WorkFlow.java # 📊 Workflow Entity
│ │ │
│ │ ├── 📁 Enum/ # 📌 Enumeration Types
│ │ │ ├── Role.java # 🎭 User Roles (ADMIN, USER)
│ │ │ ├── TaskStatus.java # 📊 Task Statuses
│ │ │ └── IssuePriority.java # ⚡ Priority Levels
│ │ │
│ │ ├── 📁 Repository/ # 💾 Data Access Layer
│ │ │ ├── UserRepository.java # 👤 User Data Access
│ │ │ ├── TaskRepository.java # ✅ Task Data Access
│ │ │ ├── IssueRepository.java # 🐛 Issue Data Access
│ │ │ └── SprintRepository.java # 🏃 Sprint Data Access
│ │ │
│ │ ├── 📁 Security/ # 🔒 Security Configuration
│ │ │ ├── JwtAuthFilter.java # 🛡️ JWT Authentication Filter
│ │ │ ├── JwtUtil.java # 🔑 JWT Utility Functions
│ │ │ └── SecurityConfiguration.java # ⚙️ Security Config
│ │ │
│ │ ├── 📁 Service/ # 🧠 Business Logic Layer
│ │ │ ├── UserService.java # 👤 User Operations
│ │ │ ├── TaskService.java # ✅ Task Operations
│ │ │ ├── IssueService.java # 🐛 Issue Operations
│ │ │ └── WorkFlowService.java # 📊 Workflow Operations
│ │ │
│ │ └── TaskManagementApplication.java # 🚀 Main Application Class
│ │
│ ├── pom.xml # 📦 Maven Configuration
│ └── README.md # 📖 Backend Documentation
│
├── 📁 frontend/
│ ├── 📁 src/
│ │ ├── 📁 api/ # 🔗 API Configuration
│ │ │ └── axios.js # 🌐 HTTP Client Setup
│ │ │
│ │ ├── 📁 components/ # 🧩 Reusable UI Components
│ │ │ ├── Navbar.jsx # 🧭 Navigation Bar
│ │ │ ├── Sidebar.jsx # 📋 Side Navigation
│ │ │ └── ProtectedRoute.jsx # 🔐 Route Protection
│ │ │
│ │ ├── 📁 pages/ # 🖥️ Application Pages
│ │ │ ├── LoginPage.jsx # 🔑 Login Interface
│ │ │ ├── RegisterPage.jsx # 📝 Registration Interface
│ │ │ ├── Dashboard.jsx # 📊 Main Dashboard
│ │ │ ├── BoardsPage.jsx # 🎯 Kanban Boards
│ │ │ └── SprintPage.jsx # 🏃 Sprint Planning
│ │ │
│ │ ├── App.jsx # ⚛️ Main Application Component
│ │ └── index.js # 🎬 Application Entry Point
│ │
│ ├── package.json # 📦 Frontend Dependencies
│ ├── vite.config.js # ⚡ Build Configuration
│ └── tailwind.config.js # 🎨 CSS Framework Config
│
├── README.md # 📖 Main Documentation
└── .gitignore # 🙈 Git Ignore Rules
```

## 📖 Usage Guide
### 1. Register & Login

 - Open the application
 - Click Register to create an account
 - Login using your credentials
### 2. Create a Project

 - Navigate to Dashboard
 - Click Create Project
 - Enter project name and description
 - Select the project to activate it
### 3. Create Board / Sprint
 - selected project
 - Click Create Board or Create Sprint
 - Configure sprint name and duration
### 4. Add Tasks / Issues
 - Click Add Task / Issue
 - Enter title, description, priority, and due date
 - Save the task
### 5. Assign Tasks
 - Select a task
 - Choose an assignee from the team members
 - Update task details
### 6. Update Task Status
 - Change status (To Do → In Progress → Done)
 - Drag and drop tasks on the board (if enabled)
### 7. Track Progress
 - View project dashboard
 - Monitor task status, priorities, and completion
### 8. Search & Filter Tasks
 - Use the search bar
 - Filter by status, priority, or assignee
   Got it 👍 — you want **API Documentation for your Task Management System**, similar to the format you shared.

Here is your **Authentication + Project + Task + Board + Sprint APIs** in the same style:

---

## 📚 API Documentation

#### Authentication

* `POST /auth/register` – Register new user
* `POST /auth/login` – User login
* `POST /auth/forgot-password` – Request password reset

#### Users

* `GET /users` – List all users
* `GET /users/{id}` – Get user by ID
* `PUT /users/{id}` – Update user profile
* `DELETE /users/{id}` – Delete user

#### Projects

* `GET /projects` – List all projects
* `POST /projects` – Create new project
* `GET /projects/{id}` – Get project details
* `PUT /projects/{id}` – Update project
* `DELETE /projects/{id}` – Delete project

#### Boards

* `GET /boards` – List all boards
* `POST /boards` – Create board
* `GET /boards/{id}` – Get board details

#### Sprints

* `GET /sprints` – List all sprints
* `POST /sprints` – Create a sprint
* `GET /sprints/{id}` – Get sprint details

#### Tasks

* `GET /tasks` – List all tasks
* `POST /tasks` – Create task
* `GET /tasks/{id}` – Get task by ID
* `PUT /tasks/{id}` – Update task
* `DELETE /tasks/{id}` – Delete task

#### Issue Linking

* `POST /issues/link` – Link two issues
* `GET /issues/links/{id}` – Get linked issues

---

You can paste this directly under your **📚 API Documentation** section in README.md.

If you want, I can also add **Request/Response examples** for each API to make your README even more professional.

## 🖼️ Application Screenshots

<div align="center">

### 🔐 Authentication
| Login Page | Registration |
|:---:|:---:|
| <img width="600" alt="Login" src="https://github.com/user-attachments/assets/4252078d-b651-41b8-b053-b59740a0a8fa" /> | <img width="600" alt="Registration" src="https://github.com/user-attachments/assets/5ac59e4c-3850-4e06-b44b-96fea7386086" /> |
| *Secure JWT-based login interface* | *User registration with role selection* |

### 📊 Dashboard & Overview
<img width="800" alt="Dashboard" src="https://github.com/user-attachments/assets/0a8e0784-90a1-42ea-ae2c-f56b3bc10498" />
<p><em>Main dashboard showing project statistics, recent activity, and team overview</em></p>

### 🎯 Task Management
| Kanban Board | Task Details |
|:---:|:---:|
| <img width="400" alt="Board View" src="https://github.com/user-attachments/assets/53ae68e5-b818-4ac0-a351-f120fd1629fc" /> | <img width="400" alt="Task Creation" src="https://github.com/user-attachments/assets/d6fa6361-4b57-4789-87b8-5b0f8ebe6def" /> |
| *Interactive Kanban board with drag-and-drop* | *Task creation and assignment interface* |

### 📋 Backlog Management
| Backlog View | Sprint Planning |
|:---:|:---:|
| <img width="400" alt="Backlog" src="https://github.com/user-attachments/assets/d1a8c788-762a-45f9-a869-6184873980e8" /> | <img width="400" alt="Sprint Backlog" src="https://github.com/user-attachments/assets/62f27586-356b-49c7-822b-b928df6b090f" /> |
| *Product backlog with prioritization* | *Sprint backlog and capacity planning* |

### 🏃 Sprint Management
<img width="800" alt="Active Sprint" src="https://github.com/user-attachments/assets/a64f47b3-e40c-435f-bc37-ed0835b3e725" />
<p><em>Active sprint tracking with progress visualization</em></p>

### 🔔 Notifications
<img width="800" alt="Notifications Panel" src="https://github.com/user-attachments/assets/31969e78-f1f8-480a-bd0a-c0962874e307" />
<p><em>Real-time notification center with activity feed</em></p>

### 📈 Workflow Management
<img width="800" alt="Workflow Configuration" src="https://github.com/user-attachments/assets/06c1f298-92b0-413d-834b-66cc51802344" />
<p><em>Custom workflow configuration and status management</em></p>

### 🔗 Integration Dashboard
<img width="800" alt="Integration Dashboard" src="https://github.com/user-attachments/assets/9d13d440-1728-475a-82e0-e4618885f57c" />
<p><em>Third-party integrations and API configuration</em></p>

### 👤 User Profile
<img width="800" alt="User Profile" src="https://github.com/user-attachments/assets/ab5b2e61-5265-4154-b72a-008eb1d54844" />
<p><em>User profile management and settings</em></p>

</div>

---

### 📱 **Key Features Showcased:**

1. **🔐 Authentication** - Secure login and registration
2. **📊 Dashboard** - Project overview with metrics
3. **🎯 Kanban Board** - Visual task management
4. **📋 Backlog** - Prioritization and planning
5. **🏃 Sprints** - Agile sprint management
6. **🔔 Notifications** - Real-time updates
7. **📈 Workflows** - Custom status configurations
8. **🔗 Integrations** - Third-party connections
9. **👤 Profiles** - User management

> 💡 *All screenshots show the actual working interface of the Task Management System with real data and interactions.*
>
> Made with ❤️ by Ranjan  
⭐ If this project will help you, give a star to this repo

