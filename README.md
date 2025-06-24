# MERN Stack Server Template

A robust and feature-rich server-side template for MERN (MongoDB, Express, React, Node.js) stack applications. This template provides a solid foundation with authentication, database connectivity, and testing setup to kickstart your full-stack web development projects.

## Features

- **Express.js Server** - Fast, unopinionated, minimalist web framework for Node.js
- **MongoDB Integration** - Connection to MongoDB Atlas with Mongoose ODM
- **Authentication** - JWT-based authentication system with cookie support
- **API Routes** - Structured API endpoints with proper routing
- **Middleware** - Essential middleware setups including CORS, cookie parsing, and authentication
- **Testing** - Complete testing environment with Vitest and MongoDB memory server
- **Development Tools** - Hot reloading, code formatting, and more

## Prerequisites

- Node.js (v16.x or higher recommended)
- MongoDB Atlas account or local MongoDB installation
- Git

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd mern-template-server
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file in the project root with the following variables:
```
PORT=5173
db_username=<your_mongodb_username>
db_password=<your_mongodb_password>
clusterName=<your_cluster_name>
db_name=<your_database_name>
JWT_KEY=<your_jwt_secret_key>
```

## Usage

### Development

Run the server in development mode with hot reloading:

```bash
npm run dev
```

### Production

Start the server in production mode:

```bash
npm start
```

### Database Initialization

Initialize the database with seed data:

```bash
npm run init_db
```

## Project Structure

```
├── __tests__/               # Test files directory
│   └── utils/               # Utility tests
├── src/                     # Source code
│   ├── db/                  # Database configuration and models
│   ├── middleware/          # Custom middleware
│   ├── routes/              # API routes
│   │   └── api/             # API endpoint definitions
│   └── utils/               # Utility functions for JWT handling and authentication
├── .env                     # Environment variables (create this file)
├── app.js                   # Application entry point
├── package.json             # Project metadata and dependencies
└── vitest.config.js         # Vitest configuration
```

## JWT Authentication Utilities

The template includes a comprehensive set of utilities for handling JWT (JSON Web Token) authentication:

- **jwt-utils.js** - Core functions for creating and verifying JWTs
  - `createJWT()` - Creates a new JWT with customizable payload and expiration
  - `getPayloadFromJWT()` - Extracts and validates the payload from a JWT

- **token-generator.js** - Advanced token management class that supports:
  - Token signing with configurable options
  - Token verification
  - Token refresh functionality for implementing token rotation

- **cookie-token.js** - Implementation of TokenGenerator configured for cookie-based authentication
  - Simplifies the process of generating tokens for HTTP-only cookies
  - Preconfigured with secure defaults (24-hour expiration)

**jwt-utils.js** is functional implementation, while **cookie-token.js** is a class-based implementation that insta the class of **token-generator.js**. You can choose either.

## API Endpoints

- `GET /` - Hello world response
- `GET /api/names` - Fetch all names from the database

## Testing

Run all tests:

```bash
npm test
```

Run tests for a specific file:

```bash
npm run test:file <file-path>
```

Generate test coverage report:

```bash
npm run test:coverage
```

## Code Formatting

Format your code with Prettier:

```bash
npm run format
```

## Environment Variables

The following environment variables must be set in your `.env` file:

| Variable      | Description                        | Default |
|---------------|------------------------------------|---------|
| PORT          | Port number for the server         | 5173    |
| db_username   | MongoDB Atlas username             |         |
| db_password   | MongoDB Atlas password             |         |
| clusterName   | MongoDB Atlas cluster name         |         |
| db_name       | MongoDB database name              |         |
| JWT_KEY       | Secret key for JWT token signing   |         |

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

