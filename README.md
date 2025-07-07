
# Loan Management System

A modular, scalable, and production-ready Loan Management System built using **.NET 8** and architected with modern enterprise design principles: **Clean Architecture (Onion)**, **CQRS**, **Domain-Driven Design (DDD)**, and **secure token-based authentication**.

---

## 🧾 About

This system manages the complete lifecycle of loans — from application to approval, disbursement, and repayment — with fine-grained user roles and authentication. Designed as a backend-first MVP, the solution is structured for future extensibility (microservices, frontend clients) and real-world deployment.

---

## 🏗️ Project Structure
```
LoanManagementSystem/
├── src/
│ ├── Business/
│ │ ├── Application/ # CQRS, Use Cases, Interfaces
│ │ ├── Domain/ # DDD Entities, VOs, Enums
│ │ ├── Infrastructure/ # EF Core, Services, Repositories
│ │ ├── Identity/ # Auth (JWT, Roles, OAuth2)
│ │ └── Shared/ # Common utilities and base types
│ └── Presentation/
│ └── API/ # ASP.NET Core Web API Entry Point
├── tests/
│ ├── UnitTests/
│ └── IntegrationTests/
├── docker-compose.yml
├── .editorconfig
└── .gitignore
```

---

## ⚙️ Architectural Stack

| Layer              | Technology / Pattern                     |
|--------------------|-------------------------------------------|
| **Framework**      | .NET 8                                    |
| **Architecture**   | Clean Architecture (Onion), DDD           |
| **Patterns**       | CQRS, MediatR, Repository, Unit of Work   |
| **ORM**            | Entity Framework Core (Code-First)        |
| **Database**       | PostgreSQL or SQL Server                  |
| **Authentication** | OAuth2 + JWT (Access & Refresh Tokens)    |
| **Authorization**  | RBAC (Role-Based Access Control)          |
| **Validation**     | FluentValidation                          |
| **API Gateway**    | YARP (Reverse Proxy)                      |
| **Logging**        | Serilog + Seq                             |
| **Rate Limiting**  | ASP.NET Core Middleware / Redis (optional)|
| **Caching**        | Redis (e.g., for token blacklisting)      |

---

## 🔐 Security

- OAuth2 Authorization Code Flow (or Password Flow for internal use)
- JWT with refresh token support
- RBAC permissions seeded via DB migrations
- Optional Redis-backed token blacklist

---

## 🚀 Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/your-org/LoanManagementSystem.git
   cd LoanManagementSystem
   ```

2. Set up environment variables:
- Create .env or use dotnet user-secrets for local dev

3. Run migrations:
   ```bash
   dotnet ef database update --project src/Business/Infrastructure
   ```
4. Launch the app:
   ```bash
   dotnet run --project src/Presentation/AP
   ```

---

## 🧪 Testing

   ```bash
   dotnet test tests/UnitTests
   dotnet test tests/IntegrationTests
   ```

---

## 📦 Roadmap

- Admin Portal UI
- Loan Scheduling Engine
- Notification Service (SMS/Email)
- Multi-tenant support
- Audit logs and user activity tracking

---

## 🛡️ License
This project is open-sourced under the MIT License.