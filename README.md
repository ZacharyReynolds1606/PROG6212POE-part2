# PROG6212POE-part2
https://youtu.be/rMlf_GUY7M4 video link
RaceDay.Api is a backend REST API for managing race events and participants. It provides endpoints for events, categories, enrolments, results, and user profiles.
The API is API-first and uses OpenAPI so clients can discover endpoints easily. Swagger UI is served at the application root for interactive testing.
DTOs and request/response contracts live in a separate Contracts project for clarity and reuse. All DTOs are public so Swagger can generate schemas.
The project uses Entity Framework Core for persistence and migrations. The database connection is configured via ConnectionStrings in app settings.
Development launch settings bind both HTTP and HTTPS ports to avoid redirect issues. The development TLS certificate must be trusted locally for HTTPS to work.
To run locally, build the solution and trust the dev certificate using dotnet dev-certs https --trust. Then run the API using the https launch profile.
Swagger JSON is available at /swagger/v1/swagger.json. The UI lets you view models and send test requests directly from the browser.
