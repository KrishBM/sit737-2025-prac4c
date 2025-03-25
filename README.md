# Enhanced Calculator Microservice

An advanced Node.js calculator microservice with Express and Winston logging, extended with additional arithmetic operations and improved error-handling strategies.

## Overview

This microservice expands upon the basic calculator by implementing additional operations, improved logging, and error-handling mechanisms.

## Features

- **Basic Arithmetic Operations**: Addition, Subtraction, Multiplication, and Division
- **Extended Functions**: Exponentiation, Square Root, and Modulo
- **Logging System**: Console and file-based logs using Winston
- **Error Handling**: Enhanced validation and error reporting
- **REST API Endpoints**: Accepts requests via URL query parameters

## Prerequisites

- Node.js and npm installed
- Git installed

## Installation Steps

1. Clone the repository:
   ```bash
   git clone https://github.com/KrishBM/sit737-2025-prac4c.git
   cd sit737-2025-prac4c
   ```

2. Initialize the Node.js project:
   ```bash
   npm init -y
   ```

3. Install dependencies:
   ```bash
   npm install express winston
   ```

4. Create an `app.js` file and add the microservice code.

## Running the Application

Start the server with:
```bash
node app.js
```

The service runs on **port 3001** (or as set in the `PORT` environment variable).

## API Endpoints

### Basic Operations

- `GET /add?num1=X&num2=Y` → Performs addition
- `GET /subtract?num1=X&num2=Y` → Performs subtraction
- `GET /multiply?num1=X&num2=Y` → Performs multiplication
- `GET /divide?num1=X&num2=Y` → Performs division

### Extended Operations

- `GET /exponent?base=X&exponent=Y` → Performs exponentiation
- `GET /sqrt?num=X` → Calculates the square root
- `GET /modulo?num1=X&num2=Y` → Computes the modulo operation

## Response Format

All operations return a JSON response:
```json
{
  "operation": "addition",
  "num1": 5,
  "num2": 3,
  "result": 8
}
```

## Error Handling

Errors return a structured JSON response:
```json
{
  "error": "Invalid numbers"
}
```

- Invalid inputs (non-numeric values) result in a `400 Bad Request`.
- Division by zero is handled with a descriptive error message.
- Server issues return a `500 Internal Server Error`.

## Logging

The application logs requests and errors using Winston:
- **Console Logging**: Real-time logs in development mode
- **File Logging**:
  - Errors logged in `logs/error.log`
  - All requests logged in `logs/combined.log`

## Error Handling Strategies

To enhance microservice resilience, the following strategies are recommended:

1. **Circuit Breaker Pattern**: Prevents repeated access to failing services by temporarily rejecting requests after a failure threshold is met.
2. **Retry Pattern**: Automatically retries failed requests, reducing transient failures using an exponential backoff strategy.
3. **Fallback Mechanism**: Provides alternative responses when the primary service is down (e.g., cached data or default values).

## Repository

- **GitHub Repository**: [SIT737-2025-prac4c](https://github.com/KrishBM/sit737-2025-prac4c)

## License

[Add your license information here]

## Contributing

[Add guidelines for contributing to the project]
