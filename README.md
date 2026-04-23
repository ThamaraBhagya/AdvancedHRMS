# Project Overview

AdvancedHRMS is a comprehensive Human Resource Management System designed to streamline HR processes and improve organizational efficiency. The system is modular, scalable, and can be tailored to fit the needs of any organization.

# Features
- Employee Management
- Payroll System
- Recruitment Module
- Performance Reviews
- Leave Management
- Reports & Analytics

# Tech Stack
- Frontend: React
- Backend: Node.js, Express
- Database: PostgreSQL
- Authentication: JWT
- Hosting: AWS

# Getting Started

## Prerequisites
- Node.js (v14 or later)
- PostgreSQL (v12 or later)
- Git

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/ThamaraBhagya/AdvancedHRMS.git
   cd AdvancedHRMS
   ```
2. Install dependencies:
   ```bash
   npm install
   ```

## Configuration
1. Create a `.env` file in the root directory.
2. Populate it with your database connection string and other environment variables.

# Usage
1. Start the development server:
   ```bash
   npm start
   ```

# Project Structure
```
AdvancedHRMS/
├── client/             # Frontend application
├── server/             # Backend application
├── scripts/            # Scripts for building, testing, etc.
├── .env                # Environment configuration
└── README.md           # Documentation
```

# Scripts/Commands
- `npm start`: Starts the server.
- `npm run build`: Builds the frontend application.
- `npm test`: Runs tests.

# Environment Variables
- `DATABASE_URL`: Connection string for the PostgreSQL database.
- `JWT_SECRET`: Secret key for JSON Web Token.
- `PORT`: Port for the server to run on.

# Database/Migrations/Seed Instructions
1. To create the database:
   ```bash
   CREATE DATABASE advanced_hrms;
   ```
2. Run migrations:
   ```bash
   npm run migrate
   ```
3. Seed the database:
   ```bash
   npm run seed
   ```

# Testing
- To run tests, execute:
   ```bash
   npm test
   ```

# Deployment
- Instructions for deploying on AWS:
   1. Build the application using `npm run build`.
   2. Set up AWS Elastic Beanstalk or EC2.
   3. Deploy the built application and ensure the environment variables are set.

# Contributing
We welcome contributions! Please read our [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

# License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

# Contact
For questions, please contact us at [email@example.com] or visit our [website](http://example.com)!
