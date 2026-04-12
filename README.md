# RailOps Booking API

RailOps Booking API is a backend service for train search, reservation, booking retrieval, and admin-managed train operations. It exposes authenticated user flows for booking and protected admin workflows for managing train inventory and route data.

## What It Does

- user registration and login
- train availability lookup between source and destination
- authenticated seat booking
- booking detail retrieval
- admin-only train creation and management
- JWT-based auth with protected routes
- API-key protected administrative operations

## Tech Stack

- Node.js
- Express
- MySQL
- Sequelize
- JWT
- bcrypt
- dotenv

## Architecture

The application is organized into:

- `src/routes`: route definitions for auth, trains, and bookings
- `src/controllers`: request handling and business logic
- `src/models`: persistence layer
- `src/middlewares`: authentication and authorization helpers
- `src/server.js`: server bootstrap

## API Surface

### Authentication

- `POST /api/auth/register`
- `POST /api/auth/login`

### Train Discovery

- `GET /api/trains?source=...&destination=...`

### Booking

- `POST /api/book`
- `GET /api/bookings/:id`

### Admin

- `POST /api/trains/admin/train`

## Local Setup

Clone and install:

```bash
git clone https://github.com/ayush-sharaf/railway-management.git
cd railway-management
npm install
```

Create `.env`:

```env
PORT=3000
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=yourpassword
DB_NAME=railway_db
JWT_SECRET=yourjwtsecret
ADMIN_API_KEY=your-admin-api-key
```

Start in development:

```bash
npm run dev
```

Start normally:

```bash
npm start
```

## Example Use Cases

- search trains between two stations
- reserve seats for an authenticated passenger
- retrieve an existing booking
- add or update train information as an administrator

## Why This Project Matters

This project is useful as a backend systems portfolio piece because it combines:

- authentication
- role separation between users and admins
- relational persistence
- booking workflows
- protected operational endpoints

It is stronger when framed as an operations-oriented booking API than as a generic “railway management assignment”.
