# Tareino Backend

Tareino is a gamified learning platform that connects academic responsibility with virtual pet progression. This repository contains the **backend service**, built with ASP.NET Core, that powers the Tareino ecosystem.

## 🎯 Purpose

Tareino addresses student motivation challenges by creating a direct feedback loop between academic performance and virtual pet progression. Students complete assignments from Google Classroom, and their virtual companion grows, evolves, and thrives based on consistent task completion.

## 🧠 Core Concept

- **Sync with Google Classroom** — Automatically pull assignments, courses, and submissions
- **Track Academic Performance** — Monitor assignment completion, grades, and deadlines  
- **Pet Progression System** — Virtual pets respond to user behavior in real time
- **Reward & Penalty System** — Unlock rewards for consistency; face consequences for missed deadlines
- **User Engagement** — Gamified features including streaks, inventory, shop, and wallet systems

## 🏗️ Architecture

Tareino Backend follows **Hexagonal Architecture** principles with a layered structure:

```
Tareino/
├── Tareino.API/              # REST API & Controllers
├── Tareino.Application/      # Business Logic & Use Cases
├── Tareino.Domain/           # Core Domain Model & Entities
├── Tareino.Infrastructure/   # Data Access & External Services
└── Tareino.Tests/            # Test Suite
```

### Layer Responsibilities

- **API Layer** (`Tareino.API`)
  - REST endpoints with Swagger documentation
  - HTTP request/response handling
  - OAuth flow implementation (Google Classroom)

- **Application Layer** (`Tareino.Application`)
  - Use case orchestration (Auth, Assignments, Pet Management, etc.)
  - DTO mapping and validation
  - Business rule enforcement

- **Domain Layer** (`Tareino.Domain`)
  - Core entities (User, Pet, Assignment, Classroom, etc.)
  - Value objects and domain logic
  - Business rules and constraints

- **Infrastructure Layer** (`Tareino.Infrastructure`)
  - Database persistence (MySQL via EF Core)
  - External API integrations (Google Classroom API)
  - Authentication & token management

## 🔌 Core Features

### Authentication & Authorization
- **Google OAuth 2.0** — Seamless login via Google accounts
- **Token Management** — Access token and refresh token handling
- **Token Service** — `TokenAccesoService` and `TokenRefreshService` for secure session management

### Google Classroom Integration
- **Course Synchronization** — Auto-sync enrolled courses from Google Classroom
- **Assignment Sync** — Retrieve coursework and track submissions
- **Submission Tracking** — Monitor student submission status and grades
- **24-Hour Scheduled Sync** — Periodic updates to keep data current

### User Management
- **User Entity** — Store user profile, auth credentials, and metadata
- **Active User Tracking** — Manage user status and last activity
- **Multi-Auth Support** — Support for both Google OAuth and traditional credentials

### Virtual Pet System
- **Pet Progression** — Pets evolve based on academic performance
- **Pet Management Use Cases** — Creation, evolution, and state management
- **Streaks System** — Track consistency and consecutive task completions
- **Inventory & Shop** — In-game items and purchasable rewards

### Gamification Features
- **Reward System** — Grant rewards for achievement milestones
- **Penalty System** — Consequences for missed deadlines
- **Wallet System** — In-game currency management
- **Group System** — Collaborative features and team challenges

## 🗄️ Database

- **MySQL** with Entity Framework Core
- **MongoDB** support configured (secondary storage)
- Entities: Users, Classrooms, Courses, Assignments, Tasks, Pets, Submissions


## ⚙️ Tech Stack

| Component | Technology |
|-----------|------------|
| **Language** | C# |
| **Framework** | ASP.NET Core (.NET 10.0) |
| **ORM** | Entity Framework Core |
| **Database** | MySQL |
| **Container** | Docker |
| **Auth** | Google OAuth 2.0 |
| **External API** | Google Classroom API |



## 📊 Project Status

### ✅ Implemented
- Backend architecture (Hexagonal Architecture layers)
- Google Classroom OAuth integration
- Token management system
- Classroom sync service (24-hour scheduled sync)
- User authentication and authorization
- Database schema and EF Core setup
- Docker containerization
- API controller structure

### 🚧 In Progress
- Use case implementations (Assignments, Pet Management, Streaks, etc.)
- Database persistence layer

### 📋 Planned
- Frontend client integration (Expo React Native)
- Advanced pet progression mechanics
- Analytics and reporting
- Performance optimization
- Comprehensive test coverage


## 🔐 Security Considerations

- **OAuth 2.0** — Google authentication for secure credential handling
- **Token Expiration** — Access tokens have limited lifetime
- **Token Refresh** — Automatic refresh token rotation
- **CORS Policy** — Currently allows all origins (configure for production)
- **API Key Authentication** — Internal API key for service-to-service communication



## 🧪 Testing

Tests are located in the `Tareino.Tests` project:

```bash
dotnet test Tareino.Tests/Tareino.Tests.csproj
```



## 📄 License

This project is licensed under the **MIT License** — see the LICENSE file for details.

## 📞 Contact & Support

For questions or issues related to the project, please contact yenarouu@gmail.com.

---

**Status**: Early Development Phase  
**Last Updated**: June 2026  
**.NET Version**: 10.0  
**MySQL Version**: 8.0+
