# PROG6212POE-part2
https://youtu.be/rMlf_GUY7M4 video link
RaceDay.Api is a backend REST API for managing race events and participants. It provides endpoints for events, categories, enrolments, results, and user profiles.
The API is API-first and uses OpenAPI so clients can discover endpoints easily. Swagger UI is served at the application root for interactive testing.
DTOs and request/response contracts live in a separate Contracts project for clarity and reuse. All DTOs are public so Swagger can generate schemas.
The project uses Entity Framework Core for persistence and migrations. The database connection is configured via ConnectionStrings in app settings.
Development launch settings bind both HTTP and HTTPS ports to avoid redirect issues. The development TLS certificate must be trusted locally for HTTPS to work.
To run locally, build the solution and trust the dev certificate using dotnet dev-certs https --trust. Then run the API using the https launch profile.
Swagger JSON is available at /swagger/v1/swagger.json. The UI lets you view models and send test requests directly from the browser.
Controller actions accept typed request bodies so POST and PUT endpoints show request models. This makes it easy to craft payloads in Swagger for testing.
Category routes follow a consistent pattern to avoid duplicate path segments. Events, enrolments, and results follow similar RESTful routing conventions.
Connection strings and secrets should be moved to environment variables or user secrets for security. Do not commit sensitive credentials to source control.
Controller methods currently return placeholder Ok responses and need business logic. Implement services and DbContext usage to persist data and handle validation.
Add model validation using data annotations or a validation library to enforce required fields. Validation improves API correctness and Swagger documentation.
Add ProducesResponseType attributes to controllers to document status codes and response shapes. This makes generated documentation clearer for consumers.
Run migrations with dotnet ef database update to create or update the database schema. Keep migrations in source control and apply them during deployment.
Tests are present in the RaceDay.Api.Tests project and should be run frequently. Use dotnet test to execute unit and integration tests locally.
For contributions, fork, create a branch, and open a pull request with tests and description of changes. Follow code conventions and include migration updates if needed.
The project aims to be reliable, secure, and easy to integrate with web or mobile clients. Focus next on implementing core business flows, validation, and comprehensive tests.
