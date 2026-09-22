# 🏠 Hunianly

> **Smart Property & Rental Management**

Hunianly is a modern property and rental management platform designed to simplify the management of rental properties, units, tenants, contracts, billing, payments, and property operations.

Built with a performance-focused and developer-friendly architecture using **Rust, SvelteKit, and PostgreSQL**.

---

## ✨ Overview

Managing rental properties can involve many repetitive tasks, from tracking available units and tenants to managing rental contracts, invoices, and payments.

**Hunianly** aims to bring these operations into a single platform.

The project is designed to support different types of rental properties, including:

* 🏠 Houses
* 🏢 Apartments
* 🛏️ Boarding houses / Kos
* 🏪 Commercial properties
* 🏘️ Other rental units

---

## 🚀 Features

### 🏢 Property Management

* Manage multiple properties
* Property information and details
* Property types
* Property addresses
* Unit management

### 🚪 Unit / Room Management

* Create and manage rental units
* Unit availability status
* Rental pricing
* Occupancy tracking
* Maintenance status

### 👤 Tenant Management

* Tenant profiles
* Contact information
* Identity information
* Rental history
* Current rental unit

### 📄 Rental Contracts

* Create rental contracts
* Rental periods
* Monthly rental prices
* Security deposits
* Contract status
* Contract expiration tracking

### 💰 Billing & Payments

* Generate rental invoices
* Track payment status
* Payment history
* Due dates
* Overdue payments
* Payment verification

### 🔧 Maintenance

* Report property or unit issues
* Track maintenance requests
* Maintenance status
* Maintenance costs
* Maintenance history

### 📊 Dashboard & Reports

* Property overview
* Occupancy statistics
* Revenue overview
* Outstanding payments
* Expense tracking
* Rental performance

### 🤖 AI Assistant

Hunianly is designed with future AI capabilities in mind.

The AI assistant can help users interact with their property data using natural language.

Example:

> "How much rental income did I receive this month?"

> "Which tenants haven't paid yet?"

> "Which units are currently vacant?"

> "Show me contracts that will expire next month."

---

## 🏗️ Architecture

Hunianly follows a modular client-server architecture.

```text
                    ┌──────────────────┐
                    │      User        │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │    SvelteKit     │
                    │    Frontend      │
                    └────────┬─────────┘
                             │
                          REST API
                             │
                             ▼
                    ┌──────────────────┐
                    │   Rust + Axum    │
                    │     Backend      │
                    └────────┬─────────┘
                             │
                           SQLx
                             │
                             ▼
                    ┌──────────────────┐
                    │   PostgreSQL     │
                    │     Database     │
                    └──────────────────┘
```

---

## 🛠️ Technology Stack

### Frontend

* [SvelteKit](https://svelte.dev/docs/kit)
* TypeScript
* Tailwind CSS
* shadcn-svelte

### Backend

* Rust
* Axum
* Tokio
* Serde
* SQLx

### Database

* PostgreSQL
* SQLx Migrations

### Development

* Git
* GitHub
* Docker
* Docker Compose
* OpenAPI
* Bruno

### Testing

* Rust `cargo test`
* Vitest
* Playwright

### AI Development

Hunianly is developed with the assistance of AI coding agents.

The development workflow is designed around:

* AI-assisted implementation
* Repository-aware coding agents
* Automated testing
* Code review
* Incremental feature development

---

## 📁 Project Structure

```text
hunianly/
│
├── frontend/
│   ├── src/
│   ├── static/
│   └── package.json
│
├── backend/
│   ├── src/
│   ├── migrations/
│   └── Cargo.toml
│
├── docs/
│   ├── architecture.md
│   ├── requirements.md
│   ├── database.md
│   ├── api.md
│   └── business-rules.md
│
├── scripts/
│
├── docker-compose.yml
├── .env.example
├── AGENTS.md
└── README.md
```

---

## 🧩 Core Modules

Hunianly is organized around several core business domains.

```text
Property
    │
    ├── Units
    │
    ├── Tenants
    │
    ├── Rental Contracts
    │
    ├── Invoices
    │
    ├── Payments
    │
    ├── Expenses
    │
    └── Maintenance
```

---

## 🗄️ Database

The initial database is centered around the following entities:

```text
users
properties
units
tenants
rental_contracts
invoices
payments
expenses
maintenance_requests
```

Relationships:

```text
User
 │
 └── Property
       │
       ├── Unit
       │    │
       │    └── Rental Contract
       │             │
       │             └── Tenant
       │
       ├── Expense
       │
       └── Maintenance Request

Rental Contract
       │
       └── Invoice
              │
              └── Payment
```

---

## 🔐 Authentication & Authorization

Hunianly is designed to support role-based access control.

Initial roles:

| Role     | Description                                            |
| -------- | ------------------------------------------------------ |
| `OWNER`  | Full property management access                        |
| `ADMIN`  | Manage properties, tenants, billing, and operations    |
| `STAFF`  | Handle operational tasks such as maintenance           |
| `TENANT` | Access personal rental information and submit requests |

---

## ⚙️ Development

### Prerequisites

Make sure you have the following installed:

* Git
* Docker
* Docker Compose
* Rust
* Node.js
* npm

### Clone the repository

```bash
git clone https://github.com/<your-username>/hunianly.git

cd hunianly
```

### Environment variables

Copy the example environment file:

```bash
cp .env.example .env
```

Configure the required variables in `.env`.

### Start the development environment

```bash
docker compose up -d
```

### Backend

```bash
cd backend

cargo run
```

### Frontend

```bash
cd frontend

npm install
npm run dev
```

---

## 🧪 Testing

### Backend

Run formatting:

```bash
cargo fmt
```

Run linting:

```bash
cargo clippy
```

Run tests:

```bash
cargo test
```

### Frontend

```bash
npm run check
npm run lint
npm run test
```

End-to-end tests:

```bash
npx playwright test
```

---

## 🤖 AI-Assisted Development

Hunianly uses AI coding agents as part of the development workflow.

AI agents are expected to follow the project instructions defined in:

```text
AGENTS.md
```

Development tasks are implemented incrementally.

Example workflow:

```text
Requirement
     ↓
Architecture
     ↓
Database
     ↓
API
     ↓
Backend
     ↓
Frontend
     ↓
Tests
     ↓
Code Review
```

AI agents should not introduce new technologies or modify the established architecture without explicit approval.

---

## 🗺️ Roadmap

### Phase 1 — Foundation

* [ ] Project setup
* [ ] Database architecture
* [ ] Authentication
* [ ] User management
* [ ] Role-based authorization

### Phase 2 — Property Management

* [ ] Property CRUD
* [ ] Unit / room management
* [ ] Property dashboard
* [ ] Occupancy tracking

### Phase 3 — Tenant Management

* [ ] Tenant CRUD
* [ ] Tenant profiles
* [ ] Rental history
* [ ] Rental contracts

### Phase 4 — Billing

* [ ] Invoice generation
* [ ] Payment tracking
* [ ] Payment verification
* [ ] Overdue tracking
* [ ] Late fees

### Phase 5 — Operations

* [ ] Expense management
* [ ] Maintenance requests
* [ ] Notifications
* [ ] Document management

### Phase 6 — Analytics

* [ ] Revenue analytics
* [ ] Expense analytics
* [ ] Occupancy analytics
* [ ] Financial reports

### Phase 7 — AI

* [ ] AI property assistant
* [ ] Natural language queries
* [ ] Financial summaries
* [ ] Payment insights
* [ ] Automated recommendations

---

## 🔒 Security

Security is treated as a core requirement of the project.

The application aims to implement:

* Secure authentication
* Password hashing
* Role-based authorization
* Input validation
* SQL injection protection
* Secure file uploads
* API rate limiting
* Environment-based secrets
* Audit logging

Sensitive credentials should never be committed to the repository.

---

## 📌 Project Status

> 🚧 **Currently in development**

Hunianly is an ongoing project and features may change as the architecture and business requirements evolve.

---

## 🎯 Vision

Hunianly aims to become a simple and powerful platform for managing rental properties without the complexity of traditional property management systems.

The long-term vision is to combine:

```text
Property Management
        +
Automation
        +
Analytics
        +
AI
```

into a single platform.

---

## 📄 License

License information will be added when the project reaches its initial stable release.

---

## 👨‍💻 Development

Built with ❤️ using:

**Rust · SvelteKit · PostgreSQL · Docker · AI**