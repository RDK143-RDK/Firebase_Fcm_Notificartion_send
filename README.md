# MyProject - .NET Backend API

This is a .NET 6 Web API project developed by **Dinesh**.  
It provides secure, scalable, and efficient backend services, with structured APIs for managing data and integrating with frontend applications. The project follows clean architecture principles and supports future enhancements like authentication, database connectivity, and external API integration.

## Features
- Built with ASP.NET Core Web API  
- RESTful endpoints  
- Scalable project structure  
- Easy integration with frontend (Angular, React, etc.)  
- Configurable environment settings  
- Ready for deployment with tools like **ngrok** or cloud hosting  

## Requirements
- .NET 6 SDK or later  
- SQL Server / PostgreSQL (optional, if using database)  
- Visual Studio / VS Code  
- Ngrok (for external API testing)  

## Setup
```bash
git clone https://github.com/your-username/myproject.git
cd myproject
dotnet restore
dotnet run
```

Default URL:  
```
http://localhost:5139
```
## 📦 Required NuGet Packages
Run these commands to install the required packages:
```bash
dotnet add package Microsoft.EntityFrameworkCore
dotnet add package Microsoft.EntityFrameworkCore.Design
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
dotnet add package Microsoft.EntityFrameworkCore.Tools
dotnet add package FirebaseAdmin
```
🛢 Database Setup
1. Configure Database Connection
In your appsettings.json, update the connection string:

json
```bash
"ConnectionStrings": {
  "DefaultConnection": "Server=localhost;Database=MyProjectDb;Trusted_Connection=True;TrustServerCertificate=True;"
}
2. Add DbContext
In ApplicationDbContext.cs:
```
csharp
```bash
using Microsoft.EntityFrameworkCore;
using MyProject.Models;

public class ApplicationDbContext : DbContext
{
    public ApplicationDbContext(DbContextOptions<ApplicationDbContext> options) : base(options) { }
    public DbSet<UserToken> UserTokens { get; set; }
}
🗄 Entity Example (UserToken.cs)
```
csharp
```bash
public class UserToken
{
    public int Id { get; set; }
    public string Token { get; set; }
    public bool IsActive { get; set; }
    public bool NotificationSent { get; set; }
}
🔧 Migration Commands
Run these commands step by step:
```


# Add initial migration
```bash
dotnet ef migrations add InitialCreate
```
# Apply migration and create database
```bash
dotnet ef database update
```

# If you change models later, add new migration
```bash
dotnet ef migrations add UpdateUserToken
```

# Apply latest migration
```bash
dotnet ef database update
```
▶ How to Run
```bash
dotnet build
dotnet run
Backend will run at:
👉 http://localhost:5139
```

If sharing with friends remotely, use ngrok:
```bash
ngrok http 5139
This gives a public URL (example):
👉 https://xxxxxx.ngrok-free.app
```

✨ Author "Dineshkumar R"


