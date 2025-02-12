# backend-database

This project is a domain-driven backend developed in **C#** using the **.NET Core** framework. Its purpose is to manage the necessary database operations for the **StarkFantasy League** system, which interacts with smart contracts hosted in the [backend-starknet-contracts](https://github.com/StarkFantasy-League/backend-starknet-contracts) repository.

## Technologies and Architecture

### Language and Framework
- **Language:** C#
- **Framework:** .NET Core
- **ORM:** Entity Framework Core
- **Database:** SQL Server
- **Architectural Pattern:** Domain-Driven Design (DDD)

### Domain-Driven Architecture
The backend follows a DDD-based structure, separating responsibilities into the following layers:

1. **Domain:**
   - Contains business entities, Value Objects, and repository interfaces.
   - Has no dependencies on other layers.

2. **Application:**
   - Contains use cases and application services.
   - Communicates with the Domain and Infrastructure layers.

3. **Infrastructure:**
   - Implements repositories and manages data persistence.
   - Defines database access configuration.
   - Includes communication with Starknet smart contracts.

4. **Presentation (API):**
   - Exposes endpoints through controllers.
   - Implements dependency injection and middleware configuration.

## Setup and Execution

### Prerequisites
- .NET SDK 8.0 or higher
- Docker (optional, for database containers)
- Access to Starknet smart contracts

### Installation and Execution
```sh
# Clone the repository
git clone https://github.com/StarkFantasy-League/backend-database.git
cd backend-database

# Restore dependencies
dotnet restore

# Configure environment variables (see .env.example)
cp .env.example .env

# Apply database migrations
dotnet ef database update

# Start the API
dotnet run
```

## Dependencies
- Entity Framework Core
- MediatR (for CQRS)
- AutoMapper (for DTO mapping)
- Serilog (for logging)

## Contribution and Repository Rules
### Working Guidelines
- Each new feature must be in a branch with the `feature/` prefix.
- Bugs are handled in `fix/` branches.
- Use PRs with a clear description of the change and reference an issue.
- Code must follow **C# coding conventions**.
- Unit tests must be written for every new feature.

### Commit Standards
```
feat: Add new feature X
fix: Fix bug in module Y
refactor: Improve code without changing functionality
chore: Update dependencies or configurations
```

## Notes
- Ensure Starknet smart contracts are updated before implementing changes.
- Keep database migrations synchronized.
- Document important changes in the code and README.

---

_**This document will be updated as the project evolves.**_


