# ATC Techrise Bootcamp Backend Capstone — Notes API

## Overview

Build a simple backend REST API for a **Notes application**.

Users should be able to register, log in, and manage their own notes.

This project is **language agnostic**. You may use any backend language or framework of your choice, including:

- Go
- Node.js
- Python
- Java
- C#
- PHP
- Rust

The goal is to demonstrate your understanding of:

- REST APIs
- Authentication
- CRUD operations
- Database usage
- Input validation
- Basic API security
- Error handling

---

## API Requirements

Build the following **10 endpoints**:

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/auth/register` | Register a new user |
| `POST` | `/api/auth/login` | Login user |
| `GET` | `/api/users/me` | Get logged-in user profile |
| `PATCH` | `/api/users/me` | Update logged-in user profile |
| `POST` | `/api/notes` | Create a note |
| `GET` | `/api/notes` | Get all notes belonging to the user |
| `GET` | `/api/notes/{id}` | Get a single note |
| `PATCH` | `/api/notes/{id}` | Update a note |
| `DELETE` | `/api/notes/{id}` | Delete a note |
| `GET` | `/api/health` | Check if the API is running |

---

## User Model

Your user should contain at least:

```text
id
name
email
password
created_at
```

> Passwords must never be stored as plain text.

---

## Note Model

A note should contain at least:

```text
id
user_id
title
content
created_at
updated_at
```

Each note must belong to a user.

---

## Authentication

Users must register and log in before accessing protected endpoints.

You may use:

- JWT
- Sessions
- Any other secure authentication method

Protected endpoints should reject unauthenticated requests with an appropriate response such as:

```text
401 Unauthorized
```

---

## Authorization

Users should only be able to access their own notes.

For example:

> User A must not be able to read, update, or delete User B's notes.

---

## Validation

Your API should validate incoming data.

At minimum:

- Name cannot be empty
- Email must be valid
- Email must be unique
- Password cannot be empty
- Note title cannot be empty
- Note content cannot be empty

---

## Security Requirements

Your application must:

- Hash passwords before storing them
- Never return passwords in API responses
- Never commit passwords or secrets to GitHub
- Use environment variables for secrets
- Validate incoming data
- Prevent users from accessing another user's notes
- Use parameterised database queries or a safe ORM

---

## Environment Variables

Create a `.env.example` file showing the environment variables required by your application.

Example:

```env
PORT=
DATABASE_URL=
JWT_SECRET=
```

Do **not** commit your real `.env` file.

---

## Database

You may use any database.

Examples:

- PostgreSQL
- MySQL
- SQLite
- MongoDB

Choose whichever database works best with your technology stack.

---

## HTTP Status Codes

Use appropriate HTTP status codes.

Examples:

```text
200 OK
201 Created
204 No Content
400 Bad Request
401 Unauthorized
403 Forbidden
404 Not Found
409 Conflict
500 Internal Server Error
```

---

## Error Responses

Return clear error messages.

Example:

```json
{
  "error": "Email already exists"
}
```

Do not expose sensitive information such as:

- Password hashes
- Database credentials
- Secret keys
- Stack traces

---

## Repository Requirements

Your completed repository should contain:

```text
README.md
.gitignore
.env.example
Source code
Database setup or migrations
```

You should also update your README with instructions explaining how to run your application.

---

## Getting Started

### 1. Clone the repository

```bash
git clone <repository-url>
cd backend-bootcamp-capstone
```

### 2. Choose your technology

Create your backend application using your preferred language and framework.

### 3. Configure your environment

Create your local `.env` file based on `.env.example`.

### 4. Build the API

Complete all **10 required endpoints**.

### 5. Test your API

You may use tools such as Postman, Insomnia, Bruno, curl, or any API client of your choice.

---

## Example Requests

### Register

```http
POST /api/auth/register
```

```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "Password123"
}
```

### Login

```http
POST /api/auth/login
```

```json
{
  "email": "john@example.com",
  "password": "Password123"
}
```

### Create a Note

```http
POST /api/notes
Authorization: Bearer <token>
```

```json
{
  "title": "Backend Bootcamp",
  "content": "Complete my capstone API."
}
```

---

## Minimum Completion Requirements

Your application must have:

- [ ] All 10 required endpoints
- [ ] User registration
- [ ] User login
- [ ] Password hashing
- [ ] Authentication
- [ ] Notes CRUD
- [ ] Database persistence
- [ ] Input validation
- [ ] Basic API security
- [ ] Proper HTTP status codes
- [ ] Setup instructions in your README

---

## Submission

1. Complete the project.
2. Push your implementation to your own GitHub repository.
3. Make sure your README explains how to run the application.
4. Submit the link to your repository.

---

## Final Goal

Keep it simple.

The goal is to demonstrate that you understand how to build a small, secure, and functional backend REST API.

**Good luck and happy coding!**
