# AdvancedHRMS

A comprehensive **Human Resource Management System** built as a Windows desktop application. AdvancedHRMS streamlines core HR operations — from employee onboarding and payroll processing to leave management and attendance tracking — through a clean role-based interface for Admins, HR staff, and Employees.

---

## Features

| Module | Description |
|---|---|
| **Employee Management** | Add, edit, and manage employee profiles including position, salary, department, and contact details |
| **Department Management** | Create and manage departments, assign managers, set budgets, and view headcount |
| **Attendance Tracking** | Record daily check-in / check-out times and calculate hours worked |
| **Leave Management** | Employees submit leave requests; HR/Admin approve or reject with reasons; visual leave calendar |
| **Payroll Processing** | Calculate net salary from basic pay, overtime, allowances, bonuses, deductions, and tax; approve and mark as paid |
| **Pay Slips** | Generate and export pay slips as PDF |
| **Reporting** | Export HR reports to Excel (`.xlsx`) and PDF |
| **Role-Based Dashboards** | Separate dashboards and access controls for Admin, HR, and Employee roles |
| **User Management** | Signup, login, password reset, role assignment, and account approval workflow |
| **Document Management** | View and manage employee documents |

---

## Tech Stack

| Layer | Technology |
|---|---|
| **UI Framework** | WPF (Windows Presentation Foundation) |
| **Language** | C# (.NET 8.0 — Windows) |
| **Database** | Microsoft SQL Server (SQL Express) |
| **ORM** | Entity Framework Core 9 |
| **Lightweight queries** | Dapper |
| **PDF generation** | QuestPDF, PDFsharp, iTextSharp |
| **Excel export** | ClosedXML |
| **Configuration** | `Microsoft.Extensions.Configuration` / `appsettings.json` |
| **Dependency Injection** | `Microsoft.Extensions.DependencyInjection` |

---

## Prerequisites

- [.NET 8 SDK](https://dotnet.microsoft.com/download/dotnet/8.0) (Windows)
- [SQL Server Express](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) (or any SQL Server edition)
- [Visual Studio 2022](https://visualstudio.microsoft.com/) (recommended) with the **".NET desktop development"** workload
- Git

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/ThamaraBhagya/AdvancedHRMS.git
cd AdvancedHRMS
```

### 2. Configure the database connection

Open `appsettings.json` and update the connection string to point to your SQL Server instance:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=YOUR_SERVER\\SQLEXPRESS;Database=HRMS;Trusted_Connection=True;TrustServerCertificate=True;"
  }
}
```

### 3. Apply database migrations

Run the following command from the project root to create the database schema:

```bash
dotnet ef database update
```

> The `Migrations/` folder contains all incremental schema changes managed by Entity Framework Core.

### 4. Build and run

#### Using Visual Studio
1. Open `AdvancedHRMS.sln`.
2. Set **AdvancedHRMS** as the startup project.
3. Press **F5** to build and launch.

#### Using the .NET CLI

```bash
dotnet build
dotnet run
```

---

## Project Structure

```
AdvancedHRMS/
├── Converters/                  # WPF value converters (e.g. StatusToBoolConverter)
├── Data/
│   └── ApplicationDbContext.cs  # EF Core database context
├── Migrations/                  # EF Core migration history
├── Models/                      # Domain entities
│   ├── Attendance.cs
│   ├── AuthService.cs
│   ├── Department.cs
│   ├── Employee.cs
│   ├── LeaveRequest.cs
│   ├── Payrolls.cs
│   └── User.cs
├── Services/                    # Business logic services
│   ├── DepartmentService.cs
│   └── PayrollService.cs
├── Views/                       # WPF windows and pages (XAML + code-behind)
│   ├── LoginWindow.xaml
│   ├── AdminDashboard.xaml
│   ├── HRDashboard.xaml
│   ├── EmployeeDashboard.xaml
│   └── ...
├── App.xaml / App.xaml.cs       # Application entry point
├── MainWindow.xaml              # Main shell window
├── appsettings.json             # Runtime configuration
└── AdvancedHRMS.csproj          # Project file
```

---

## User Roles

| Role | Access |
|---|---|
| **Admin** | Full access: manage all employees, departments, users, roles, payroll, reports |
| **HR** | Manage employees, approve/reject leave, process payroll, view reports |
| **Employee** | View own profile, submit leave requests, view pay slips, track attendance |

New accounts require Admin approval before they can log in.

---

## Database Migrations

To create a new migration after modifying a model:

```bash
dotnet ef migrations add <MigrationName>
dotnet ef database update
```

To revert to a previous migration:

```bash
dotnet ef database update <PreviousMigrationName>
```

---

## NuGet Packages

| Package | Version | Purpose |
|---|---|---|
| `Microsoft.EntityFrameworkCore.SqlServer` | 9.0.3 | SQL Server ORM |
| `Microsoft.EntityFrameworkCore.Tools` | 9.0.3 | EF Core CLI tools (migrations) |
| `Dapper` | 2.1.66 | Lightweight SQL queries |
| `QuestPDF` | 2025.4.0 | PDF document generation |
| `PDFsharp` | 6.1.1 | PDF manipulation |
| `iTextSharp.LGPLv2.Core` | 3.7.2 | PDF generation |
| `ClosedXML` | 0.104.2 | Excel (`.xlsx`) export |
| `Microsoft.Extensions.Configuration.Json` | 9.0.3 | JSON-based configuration |
| `Microsoft.Extensions.DependencyInjection` | 9.0.3 | Dependency injection |

---

## Contributing

Contributions are welcome! To contribute:

1. Fork the repository.
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m "Add your feature"`
4. Push to your fork: `git push origin feature/your-feature-name`
5. Open a Pull Request against `main`.

Please follow the existing code style and ensure your changes don't break existing functionality.

---

## License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.

---

## Contact

For questions or feedback, please open a [GitHub Issue](https://github.com/ThamaraBhagya/AdvancedHRMS/issues).
