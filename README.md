# seatLocker 🎟️

A robust backend platform for a movie ticket booking system. This project focuses on high-concurrency seat booking, secure authentication, and a scalable modular architecture.

## 🚀 Features

- **Secure Authentication:** JWT-based login and registration with hashed credentials.
- **Race Condition Prevention:** Implements PostgreSQL row-level locking (`FOR UPDATE`) to ensure a seat cannot be double-booked by two users simultaneously.
- **Modular Architecture:** Organized into `common` (shared logic) and `modules` (feature-specific logic) for clean code separation.
- **Data Validation:** Strict input validation using **Zod** DTOs.
- **Security Middleware:** Includes authentication guards, rate limiting, and CORS protection.

## 🛠️ Tech Stack

- **Runtime:** Node.js (ES Modules)
- **Framework:** Express.js
- **Database:** PostgreSQL (using `pg` pool)
- **Validation:** Zod
- **Security:** JSON Web Tokens (JWT), Dotenv

## 📂 Project Structure

```text
/backend
  ├── /common
  │    ├── /config      # DB connection pool configuration
  │    ├── /DTO         # Zod schemas & BaseDto class
  │    ├── /middleware  # Auth guard & validation logic
  │    └── /utils       # JWT helpers
  ├── /modules
  │    ├── /auth        # Registration & Login logic
  │    └── /booking     # Seat selection & transaction logic
  └── index.mjs         # Entry point
