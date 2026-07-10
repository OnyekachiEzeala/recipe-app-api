# recipe-app-api

A production-ready RESTful API built with **Django**, **Django REST Framework**, **PostgreSQL**, and **Docker** for managing recipes, ingredients, and tags.

The API allows users to securely register, authenticate, and manage their own recipes. Each authenticated user has access only to the recipes, ingredients, and tags they create, making the application suitable as the backend for recipe management systems, meal planning applications, or food-related services.
---
## Features

- User registration and token authentication
- CRUD operations for recipes
- Ingredient and tag management
- Image uploads
- PostgreSQL
- Docker & Docker Compose
- Swagger/OpenAPI documentation
---
## Tech Stack

| Technology            | Purpose                       |
| --------------------- | ----------------------------- |
| Python                | Programming Language          |
| Django                | Web Framework                 |
| Django REST Framework | REST API Development          |
| PostgreSQL            | Database                      |
| Docker                | Containerization              |
| Docker Compose        | Multi-container orchestration |
| DRF Spectacular       | OpenAPI/Swagger Documentation |
| Pillow                | Image Processing              |
| uWSGI                 | Production WSGI Server        |
---
## Project Structure
```
recipe-app-api/
│
├── app/
│   ├── app/                # Django project settings
│   ├── core/               # Custom user model & shared utilities
│   ├── recipe/             # Recipe application
│   ├── user/               # Authentication APIs
│   ├── manage.py
│
├── docker-compose.yml
├── Dockerfile
├── requirements.txt
├── .env.sample
└── README.md
```
---
## Authentication

Authentication is implemented using **Token Authentication**.

After creating an account:

1. Login using

```bash
POST /api/user/token/
```

2. Copy the returned token.
3. Include it in the authentication header.

```bash
Authorization: Token YOUR_TOKEN
```
---
## Getting Started

```bash
git clone https://github.com/OnyekachiEzeala/recipe-app-api.git
cd recipe-app-api
docker-compose build
docker-compose up
```
---
## Database Migrations

To create new migrations

```bash
docker-compose run --rm app sh -c "python manage.py makemigrations"
```

Apply migrations

```bash
docker-compose run --rm app sh -c "python manage.py migrate"
```
---
## API Documentation

The project uses drf-spectacular to generate OpenAPI documentation.

Swagger UI

```bash
http://localhost:8000/api/docs/
```

OpenAPI Schema

```bash
http://localhost:8000/api/schema/
```
---
## Running Tests

```bash
docker-compose run --rm app sh -c "python manage.py test"
```
---
## Author

Samuel Ezeala

https://github.com/OnyekachiEzeala
