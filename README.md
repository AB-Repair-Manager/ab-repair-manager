# AB Repair Manager

A comprehensive repair management system built with .NET MAUI, designed to streamline repair operations, customer management, inventory tracking, and business reporting.

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Project Structure](#project-structure)
- [Installation Instructions](#installation-instructions)
- [Usage Guide](#usage-guide)
- [Architecture Overview](#architecture-overview)
- [Database Design](#database-design)
- [API Endpoints](#api-endpoints)
- [Contributing Guidelines](#contributing-guidelines)
- [Contact Information](#contact-information)

## 🎯 Project Overview

AB Repair Manager is a full-featured business management application designed specifically for repair shops and service centers. It provides an integrated platform for managing repair jobs, tracking customers, managing inventory, processing sales, generating invoices, and creating comprehensive business reports.

The application is built with .NET MAUI, enabling cross-platform deployment on Windows, macOS, iOS, and Android from a single codebase.

### Key Objectives

- Streamline repair workflow management
- Enhance customer relationship management
- Optimize inventory and product management
- Simplify sales and invoicing processes
- Provide actionable business insights through reporting
- Manage employee work assignments and tracking

## ✨ Features

### Repair Management
- Create and manage repair tickets/jobs
- Track repair status (pending, in-progress, completed, cancelled)
- Assign repairs to employees
- Estimate repair costs and timelines
- Add repair notes and technical details
- Track parts and materials used

### Customer Tracking
- Maintain comprehensive customer database
- Store contact information and history
- Track customer repair history
- Manage customer preferences and notes
- Support multiple contact methods (phone, email, address)

### Products & Inventory
- Manage product/parts inventory
- Track stock levels and reorder points
- Categorize products
- Monitor product pricing
- Set up automatic low-stock alerts
- Track inventory movements

### Sales Management
- Create and manage sales orders
- Track sales by product and period
- Manage pricing and discounts
- Link sales to customer records
- Generate sales reports and analytics

### Invoicing System
- Generate professional invoices
- Track invoice status (draft, sent, paid, overdue)
- Support partial payments
- Automated invoice numbering
- Email invoice functionality
- Payment history tracking

### Reporting & Analytics
- Generate comprehensive business reports
- Track sales performance by period
- Analyze repair trends and statistics
- Monitor employee productivity
- Customer acquisition and retention metrics
- Inventory analytics and forecasting

### Employee Management
- Manage employee profiles and contact information
- Track employee work assignments
- Monitor employee productivity
- Manage employee roles and permissions
- Track employee certifications and specialties

## 🛠 Technology Stack

### Frontend
- **.NET MAUI** - Cross-platform UI framework
- **XAML** - User interface markup
- **C#** - Primary programming language
- **MVVM Toolkit** - Architecture pattern implementation

### Backend
- **ASP.NET Core** - Web API framework
- **Entity Framework Core** - ORM for database access
- **C#** - Server-side logic

### Database
- **SQL Server** or **SQLite** - Data persistence
- **Entity Framework Migrations** - Database versioning

### Additional Libraries
- **Newtonsoft.Json** - JSON serialization
- **AutoMapper** - Object mapping
- **Serilog** - Logging framework
- **FluentValidation** - Data validation

### Development Tools
- **Visual Studio 2022** - IDE
- **Git** - Version control
- **Azure DevOps** - CI/CD pipeline

## 📁 Project Structure

```
ab-repair-manager/
├── src/
│   ├── AB.RepairManager.Mobile/
│   │   ├── Views/
│   │   │   ├── RepairViews/
│   │   │   ├── CustomerViews/
│   │   │   ├── ProductViews/
│   │   │   ├── SalesViews/
│   │   │   ├── InvoiceViews/
│   │   │   ├── ReportViews/
│   │   │   └── EmployeeViews/
│   │   ├── ViewModels/
│   │   ├── Models/
│   │   ├── Services/
│   │   ├── Resources/
│   │   └── App.xaml.cs
│   ├── AB.RepairManager.API/
│   │   ├── Controllers/
│   │   │   ├── RepairController.cs
│   │   │   ├── CustomerController.cs
│   │   │   ├── ProductController.cs
│   │   │   ├── SalesController.cs
│   │   │   ├── InvoiceController.cs
│   │   │   ├── ReportController.cs
│   │   │   └── EmployeeController.cs
│   │   ├── Services/
│   │   ├── Models/
│   │   ├── Data/
│   │   └── Startup.cs
│   └── AB.RepairManager.Data/
│       ├── Context/
│       ├── Migrations/
│       ├── Entities/
│       └── Repositories/
├── tests/
│   ├── AB.RepairManager.UnitTests/
│   └── AB.RepairManager.IntegrationTests/
├── docs/
├── .gitignore
├── README.md
└── LICENSE
```

## 🚀 Installation Instructions

### Prerequisites

- **.NET 8.0 SDK** or later
- **Visual Studio 2022** (Community, Professional, or Enterprise)
- **SQL Server 2019** or later (or SQLite for development)
- **Git**

### Step 1: Clone the Repository

```bash
git clone https://github.com/AB-Repair-Manager/ab-repair-manager.git
cd ab-repair-manager
```

### Step 2: Install Dependencies

```bash
dotnet restore
```

### Step 3: Configure Database Connection

Edit `appsettings.json` in the API project:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=localhost;Database=ABRepairManager;Trusted_Connection=true;"
  }
}
```

### Step 4: Run Database Migrations

```bash
cd src/AB.RepairManager.API
dotnet ef database update
```

### Step 5: Build the Solution

```bash
dotnet build
```

### Step 6: Run the Application

**For API:**
```bash
cd src/AB.RepairManager.API
dotnet run
```

**For Mobile App:**
```bash
cd src/AB.RepairManager.Mobile
dotnet maui run
```

## 📖 Usage Guide

### Getting Started

1. **Launch the Application** - Start the mobile app or web interface
2. **Create User Account** - Register with your business credentials
3. **Configure Basic Settings** - Set up company information and preferences
4. **Add Products** - Populate your inventory database
5. **Add Customers** - Begin adding customer records
6. **Create Repair Jobs** - Start managing repairs

### Main Workflows

#### Repair Management Workflow
1. Register incoming repair request
2. Create repair ticket with customer and item details
3. Assign to employee and set estimated completion
4. Update status as work progresses
5. Complete repair and generate invoice

#### Invoicing Workflow
1. Link repair/sales to invoice
2. Verify items and pricing
3. Apply discounts if applicable
4. Send to customer
5. Track payment status

#### Reporting Workflow
1. Navigate to Reports section
2. Select report type (Sales, Repairs, Customer, Employee)
3. Set date range and filters
4. Generate and export report

## 🏗 Architecture Overview

### Layered Architecture

```
┌─────────────────────────────────┐
│   Presentation Layer (MAUI)     │
│   (Views & ViewModels)          │
└─────────────────────────────────┘
              ↓
┌─────────────────────────────────┐
│   Application Layer (API)        │
│   (Controllers & Services)       │
└─────────────────────────────────┘
              ↓
┌─────────────────────────────────┐
│   Business Logic Layer           │
│   (Business Services)            │
└─────────────────────────────────┘
              ↓
┌─────────────────────────────────┐
│   Data Access Layer              │
│   (Repositories & EF Core)       │
└─────────────────────────────────┘
              ↓
┌─────────────────────────────────┐
│   Database Layer                 │
│   (SQL Server / SQLite)          │
└─────────────────────────────────┘
```

### Design Patterns

- **Repository Pattern** - Data access abstraction
- **MVVM Pattern** - UI architecture
- **Dependency Injection** - Loose coupling
- **Service Locator** - Service management
- **Factory Pattern** - Object creation
- **Observer Pattern** - Event handling

## 💾 Database Design

### Core Entities

#### Customers
```sql
CREATE TABLE Customers (
    CustomerId INT PRIMARY KEY IDENTITY,
    FirstName NVARCHAR(100) NOT NULL,
    LastName NVARCHAR(100) NOT NULL,
    Email NVARCHAR(100),
    PhoneNumber NVARCHAR(20),
    Address NVARCHAR(255),
    City NVARCHAR(100),
    State NVARCHAR(50),
    ZipCode NVARCHAR(10),
    CreatedDate DATETIME DEFAULT GETDATE(),
    ModifiedDate DATETIME
);
```

#### Repairs
```sql
CREATE TABLE Repairs (
    RepairId INT PRIMARY KEY IDENTITY,
    CustomerId INT NOT NULL,
    EmployeeId INT,
    ItemDescription NVARCHAR(255) NOT NULL,
    Status NVARCHAR(50) DEFAULT 'Pending',
    EstimatedCost DECIMAL(10, 2),
    ActualCost DECIMAL(10, 2),
    CreatedDate DATETIME DEFAULT GETDATE(),
    CompletedDate DATETIME,
    Notes NVARCHAR(MAX),
    FOREIGN KEY (CustomerId) REFERENCES Customers(CustomerId),
    FOREIGN KEY (EmployeeId) REFERENCES Employees(EmployeeId)
);
```

#### Products
```sql
CREATE TABLE Products (
    ProductId INT PRIMARY KEY IDENTITY,
    ProductName NVARCHAR(255) NOT NULL,
    Description NVARCHAR(MAX),
    Category NVARCHAR(100),
    Price DECIMAL(10, 2) NOT NULL,
    StockQuantity INT DEFAULT 0,
    ReorderLevel INT,
    CreatedDate DATETIME DEFAULT GETDATE()
);
```

#### Invoices
```sql
CREATE TABLE Invoices (
    InvoiceId INT PRIMARY KEY IDENTITY,
    CustomerId INT NOT NULL,
    RepairId INT,
    InvoiceNumber NVARCHAR(50) UNIQUE NOT NULL,
    InvoiceDate DATETIME DEFAULT GETDATE(),
    DueDate DATETIME,
    TotalAmount DECIMAL(10, 2) NOT NULL,
    PaidAmount DECIMAL(10, 2) DEFAULT 0,
    Status NVARCHAR(50) DEFAULT 'Draft',
    Notes NVARCHAR(MAX),
    FOREIGN KEY (CustomerId) REFERENCES Customers(CustomerId),
    FOREIGN KEY (RepairId) REFERENCES Repairs(RepairId)
);
```

#### Employees
```sql
CREATE TABLE Employees (
    EmployeeId INT PRIMARY KEY IDENTITY,
    FirstName NVARCHAR(100) NOT NULL,
    LastName NVARCHAR(100) NOT NULL,
    Email NVARCHAR(100),
    PhoneNumber NVARCHAR(20),
    Position NVARCHAR(100),
    HireDate DATETIME,
    Specialties NVARCHAR(MAX),
    IsActive BIT DEFAULT 1,
    CreatedDate DATETIME DEFAULT GETDATE()
);
```

### Relationships

- **Customers** ↔ **Repairs** (1:N)
- **Employees** ↔ **Repairs** (1:N)
- **Customers** ↔ **Invoices** (1:N)
- **Repairs** ↔ **Invoices** (1:N)
- **Products** ↔ **Sales** (1:N)
- **Customers** ↔ **Sales** (1:N)

## 🔌 API Endpoints

### Repair Endpoints

```
GET    /api/repairs                      - Get all repairs
GET    /api/repairs/{id}                 - Get repair by ID
POST   /api/repairs                      - Create new repair
PUT    /api/repairs/{id}                 - Update repair
DELETE /api/repairs/{id}                 - Delete repair
GET    /api/repairs/status/{status}      - Get repairs by status
```

### Customer Endpoints

```
GET    /api/customers                    - Get all customers
GET    /api/customers/{id}               - Get customer by ID
POST   /api/customers                    - Create new customer
PUT    /api/customers/{id}               - Update customer
DELETE /api/customers/{id}               - Delete customer
GET    /api/customers/{id}/repairs       - Get customer's repairs
GET    /api/customers/{id}/invoices      - Get customer's invoices
```

### Product Endpoints

```
GET    /api/products                     - Get all products
GET    /api/products/{id}                - Get product by ID
POST   /api/products                     - Create new product
PUT    /api/products/{id}                - Update product
DELETE /api/products/{id}                - Delete product
GET    /api/products/lowstock            - Get low stock items
```

### Invoice Endpoints

```
GET    /api/invoices                     - Get all invoices
GET    /api/invoices/{id}                - Get invoice by ID
POST   /api/invoices                     - Create new invoice
PUT    /api/invoices/{id}                - Update invoice
DELETE /api/invoices/{id}                - Delete invoice
POST   /api/invoices/{id}/payment        - Record payment
GET    /api/invoices/customer/{customerId} - Get customer invoices
```

### Sales Endpoints

```
GET    /api/sales                        - Get all sales
GET    /api/sales/{id}                   - Get sale by ID
POST   /api/sales                        - Create new sale
PUT    /api/sales/{id}                   - Update sale
DELETE /api/sales/{id}                   - Delete sale
GET    /api/sales/period/{startDate}/{endDate} - Get sales by period
```

### Employee Endpoints

```
GET    /api/employees                    - Get all employees
GET    /api/employees/{id}               - Get employee by ID
POST   /api/employees                    - Create new employee
PUT    /api/employees/{id}               - Update employee
DELETE /api/employees/{id}               - Delete employee
GET    /api/employees/{id}/repairs       - Get employee's repairs
```

### Report Endpoints

```
GET    /api/reports/sales                - Sales report
GET    /api/reports/repairs              - Repairs report
GET    /api/reports/customers            - Customer analytics
GET    /api/reports/employees            - Employee productivity
GET    /api/reports/inventory            - Inventory status
GET    /api/reports/financial            - Financial summary
```

## 🤝 Contributing Guidelines

We welcome contributions to AB Repair Manager! Please follow these guidelines:

### Getting Started

1. Fork the repository
2. Clone your fork: `git clone https://github.com/your-username/ab-repair-manager.git`
3. Create a feature branch: `git checkout -b feature/your-feature-name`
4. Make your changes
5. Commit your changes: `git commit -m "Add feature: description"`
6. Push to your fork: `git push origin feature/your-feature-name`
7. Create a Pull Request

### Code Standards

- Follow C# coding conventions (PascalCase for public members, camelCase for private)
- Write meaningful commit messages
- Add comments for complex logic
- Include unit tests for new features
- Ensure all tests pass before submitting PR
- Update documentation as needed

### Pull Request Process

1. Update the README.md with any new features or changes
2. Include a clear description of changes
3. Reference any related issues
4. Ensure code builds successfully
5. Request review from maintainers
6. Address review feedback promptly

### Issue Reporting

When reporting bugs:
- Provide a clear description
- Include reproduction steps
- Specify your environment (OS, .NET version)
- Attach screenshots or logs if applicable

### Feature Requests

- Describe the feature and its use case
- Explain the expected behavior
- Provide examples if helpful
- Discuss potential implementation approach

## 📧 Contact Information

### Project Maintainer
- **Name:** Ayoub Hacking
- **GitHub:** [@AyoubHacking](https://github.com/AyoubHacking)

### Support & Communication

- **GitHub Issues:** [Report bugs and request features](https://github.com/AB-Repair-Manager/ab-repair-manager/issues)
- **Email:** Contact via GitHub profile
- **Documentation:** See `/docs` directory for detailed guides

### Project Links

- **Repository:** https://github.com/AB-Repair-Manager/ab-repair-manager
- **Discussions:** https://github.com/AB-Repair-Manager/ab-repair-manager/discussions

---

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- Built with [.NET MAUI](https://github.com/dotnet/maui)
- Powered by [ASP.NET Core](https://github.com/dotnet/aspnetcore)
- Data access via [Entity Framework Core](https://github.com/dotnet/efcore)

---

**Last Updated:** December 9, 2025  
**Version:** 1.0.0  
**Status:** Active Development
