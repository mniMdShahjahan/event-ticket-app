# Event Ticket Platform

A full-stack event ticket management application built with **Spring Boot, React, Vite, PostgreSQL, and Keycloak**.

The platform allows event organizers to create and manage events, attendees to purchase tickets, and event staff to scan ticket QR codes for event entry. Authentication and authorization are handled using Keycloak.

## Features

- **Event Management:** Organizers can create and manage events.
- **Ticket Booking:** Attendees can purchase tickets for available events.
- **QR Code Tickets:** Tickets can be verified by scanning QR codes.
- **Authentication:** Secure authentication and authorization using Keycloak.
- **REST API:** A Spring Boot backend provides the application's API.
- **Modern Frontend:** A React application powered by Vite.

## Tech Stack

| Component | Technology |
|---|---|
| Backend | Java 21, Spring Boot 3.4.4 |
| Frontend | React, Vite |
| Database | PostgreSQL |
| Authentication | Keycloak |
| Database Management | Adminer |
| Build Tool | Maven |
| Package Manager | npm |

## Project Structure

```text
event-ticket-platform/
├── docs/       # Project documentation
├── backend/    # Spring Boot backend
├── frontend/   # React frontend
└── README.md   # Project documentation
```

## Prerequisites

Before running the application, make sure you have installed:

- **JDK 21**
- **Node.js 20 or later**
- **Docker and Docker Compose**
- **Git**

## Getting Started

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd <repository-folder>
```

Replace the repository URL and folder name with your own project details.

### 2. Start the Backend Services

Navigate to the backend directory and start the supporting services:

```bash
cd backend
docker compose up -d
```

This starts the configured services, including PostgreSQL, Adminer, and Keycloak.

### 3. Run the Spring Boot Backend

In the same backend directory, run:

```bash
./mvnw spring-boot:run
```

On Windows, use:

```bash
mvnw.cmd spring-boot:run
```

The backend runs on port `8080` by default, subject to the application configuration.

### 4. Configure Keycloak

Configure Keycloak with the realm and client expected by the application:

- **Realm:** `event-ticket-platform`
- **Client:** `event-ticket-platform-app`

Ensure the Keycloak issuer URI in the backend configuration matches the configured realm. Also verify the OpenID Connect configuration in `frontend/src/main.tsx`.

For local development, Keycloak is available at:

http://localhost:9090

### 5. Run the Frontend

Open a second terminal and navigate to the frontend directory:

```bash
cd frontend
npm install
npm run dev
```

Open the application in your browser:

http://localhost:5173

The frontend is configured to proxy API requests to the backend on port `8080`.

## Development Services

| Service | Address |
|---|---|
| Frontend | http://localhost:5173 |
| Backend API | http://localhost:8080 |
| Keycloak | http://localhost:9090 |
| Adminer | http://localhost:8888 |
| PostgreSQL | localhost:5432 |

These addresses assume the default local development configuration.

## Important Notes

### Java and Spring Boot Compatibility

This project is configured for **Java 21** and **Spring Boot 3.4.4**. Using other versions may require changes to the code or configuration.

### Security

This project is intended for local development and learning. Before deploying it to production:

- Change all default usernames and passwords.
- Store credentials and secrets in environment variables or a secure secrets manager.
- Configure Keycloak with secure production settings.
- Restrict database and administrative service access.
- Enable HTTPS and appropriate network security.
- Add comprehensive testing, validation, logging, and monitoring.

**Do not expose development credentials or services to the public internet.**

## Contributing

Contributions, bug reports, and suggestions are welcome. Please open an issue or submit a pull request through your repository.

## License

Please refer to the repository's `LICENSE` file for applicable licensing terms. Ensure that the license accurately reflects the permissions you have to distribute and modify the code and documentation.

## Contact

**Maintainer:** Md Shahjahan

**Email:** shahjahanknj@gmail.com
