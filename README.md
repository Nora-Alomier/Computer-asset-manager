# Assetly - Computer Asset Management System

Assetly is a student project developed for **SE 411: Software Construction**. The project was completed by a team of five students and demonstrates how a React frontend can communicate with a Spring Boot REST API.

The application helps an organization keep track of its computer assets. Users can view the inventory, search for a computer, add a new computer, update existing information, and delete a computer record. The inventory page also includes filters, pagination, summary information, and CSV export.

## Project Features

- View computer assets in an organized table.
- Search for a computer by asset ID or other information.
- Add a new computer through a validated form.
- Update an existing computer record.
- Delete a computer after confirmation.
- Filter computers by status and category.
- Display five records per page.
- View inventory statistics on the dashboard.
- Export the current inventory to a CSV file.
- Store sample records in an H2 database.

## Technologies

### Frontend

- React
- JavaScript and JSX
- Vite
- CSS
- Vitest and React Testing Library

### Backend

- Java 17
- Spring Boot
- Spring Web
- Spring Data JDBC
- H2 Database
- Maven
- JUnit 5 and Mockito

## Project Structure

```text
Computer-asset-manager/
├── backend/
│   ├── src/main/java/        Spring Boot source code
│   ├── src/main/resources/   application.properties, schema.sql, and data.sql
│   ├── src/test/java/        JUnit and Mockito tests
│   └── pom.xml
├── src/
│   ├── components/           React components
│   ├── data/                 Frontend options and sample definitions
│   ├── services/             REST API requests
│   ├── utils/                Validation and filtering functions
│   └── App.jsx
├── docs/                     Project documentation
├── package.json
└── README.md
```

The backend follows the same simple structure used in the course labs:

```text
Controller -> Service -> Repository -> H2 Database
```

## REST API

| Operation | Method | Endpoint |
|---|---|---|
| Add a computer | POST | `/api/v1/computers` |
| Retrieve all computers | GET | `/api/v1/computers/all` |
| Retrieve paginated computers | GET | `/api/v1/computers?page=0&size=5` |
| Find a computer by ID | GET | `/api/v1/computers/{id}` |
| Update a computer | PUT | `/api/v1/computers/{id}` |
| Delete a computer | DELETE | `/api/v1/computers/{id}` |

## Running the Project

### 1. Start the Spring Boot Server

Java 17 is recommended because it matches the course setup.

```bash
cd backend
./mvnw spring-boot:run
```

The backend runs at `http://localhost:8080`.

### 2. Start the React Application

Open another terminal in the main project folder:

```bash
npm install
npm run dev
```

Open `http://localhost:5173` in a browser.

## Running the Tests

Backend tests:

```bash
cd backend
./mvnw test
```

Frontend tests:

```bash
npm test
```

At the time of submission, all 12 backend tests and all 10 frontend tests passed successfully.

## Database Files

The backend uses an in-memory H2 database. The table and initial data are created when the server starts:

- `backend/src/main/resources/schema.sql` creates the computer asset table.
- `backend/src/main/resources/data.sql` inserts the sample computer records.

Because H2 is used in memory, the database returns to its original sample data whenever the backend restarts.

## Course Information

- Course: SE 411 - Software Construction
- Project: Computer Asset Management System
- Team: Five students
- Academic Year: 2026-2027

This repository was prepared as a course project and focuses on clear, understandable code based on the examples practiced in the course laboratories.
