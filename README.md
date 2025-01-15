**Store API**

Overview
Store API is a backend application built using the .NET 8 framework. It applies best practices in Domain-Driven Design (DDD), CQRS, and clean architecture. The application is designed for real-world scenarios and includes robust testing and containerization for easy deployment.


**Features**
Domain-Driven Design (DDD) to model complex business logic.
CQRS for separation of commands and queries.
MediatR for command, query, and notification handling.
Database migrations with Entity Framework Core.
Comprehensive testing using xUnit, Moq, and FluentAssertions.
ErrorOr for standardized error handling.
Docker support for containerization

**Technologies Used**

.NET 8
Entity Framework Core
MediatR
xUnit, Moq, FluentAssertions
ErrorOr
Docker

**Getting Started**
Prerequisites
Ensure you have the following installed:

.NET SDK 8
Docker
SQL Server

Installation
Clone the repository:

```
git clone https://github.com/lucasbusto/store.git
cd store
```

Restore dependencies:

```
dotnet restore
```

Set up your database connection string in appsettings.json or appsettings.Development.json:
appsettings.Development.json

```
{
    "ConnectionStrings": {
        "SqlServer": "Server=localhost;Database=store_db;Trusted_Connection=True;TrustServerCertificate=True;"
    }
}
```

**Usage**
Running Locally
Apply database migrations:

```
dotnet ef database update --project Infrastructure --startup-project Store.API
```
Start the application

```
dotnet run --project Store.API
```
Access the Swagger API documentation at:
https://localhost:5001/swagger

Running with Docker
Build and run the Docker containers:

```
docker-compose up
```
The application will be accessible at:
```
http://localhost:5000
```

Testing
Run all unit tests with:

```
dotnet test
```

The project uses:
xUnit for unit testing.
Moq for mocking dependencies.
FluentAssertions for readable assertions.

**Architecture**
The application follows the clean architecture pattern, structured into layers:
Presentation: Handles HTTP requests and user interactions.
Application: Contains commands, queries, and business logic.
Domain: Core business logic, aggregates, and domain events.
Infrastructure: Data access, external services, and persistence.












