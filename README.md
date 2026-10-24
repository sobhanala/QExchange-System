# QExchange

A collaborative Go backend for a cryptocurrency-exchange coursework project. It includes user accounts, authentication, banking information, support tickets, cryptocurrency management, and trading-related APIs.

## Stack and structure

- Go 1.21.3, Echo, GORM, and PostgreSQL.
- `handlers/`, `server/`: HTTP handlers and route registration.
- `services/`, `models/`: application logic and data models.
- `database/`: connections and demonstration seed data.
- `middlewares/`: authentication and access checks.
- `docs/`: generated Swagger documentation.
- `test/`: existing service tests.

## Run locally

Install Docker with Compose support. Review the database and authentication configuration before starting; any committed environment values are historical development settings and must be replaced for a real deployment.

```sh
git clone https://github.com/sobhanala/QExchange-System.git
cd QExchange-System
docker compose up --build
```

The original configuration exposes the API at `http://localhost:8080`. Open `/swagger/index.html` for API documentation. Startup applies migrations and inserts demonstration data when the user table is empty.

For a native Go launch, review `database/connection.go` and the seed SQL path in `main.go`; the container image supplies files expected by the original startup layout.

## Existing tests and docs

```sh
go test ./test
swag init --parseDependency
```

Tests require the dependencies and database setup used by their fixtures. Documentation generation requires the Swag CLI. These commands were identified from the source; a complete exchange deployment has not been validated by this README update.

This is a coursework prototype and has not been audited for handling real funds.

## Project credits

This is Sobhan Alaeddini's portfolio fork of [Quera-Go-Zilla/QExchange-System](https://github.com/Quera-Go-Zilla/QExchange-System). The project was developed collaboratively; the upstream repository and Git history retain the original contributor credits. Documentation in this fork is maintained independently.
