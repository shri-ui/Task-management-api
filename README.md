# Task Management API

## Overview
This Task Management API is a Django-based RESTful service that allows users to create, read, update, and delete tasks. It provides a robust backend for task management applications, featuring user authentication, task prioritization, and filtering capabilities.

## Features
- User authentication (register, login, logout)
- CRUD operations for tasks
- Task filtering and sorting
- Priority levels for tasks
- Due date management
- PostgreSQL database integration

## Technologies Used
- Django
- Django REST Framework
- PostgreSQL
- JWT for authentication

## Setup and Installation

1. Clone the repository:
   ```
   git clone [your-repository-url]
   cd task_management_api
   ```

2. Set up a virtual environment:
   ```
   python -m venv .venv
   source .venv/bin/activate  # On Windows use `.venv\Scripts\activate`
   ```

3. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

4. Set up PostgreSQL:
   - Install PostgreSQL
   - Create a database named `task_management_db`

5. Configure the database in `settings.py`:
   ```python
   DATABASES = {
       'default': {
           'ENGINE': 'django.db.backends.postgresql',
           'NAME': 'task_management_db',
           'USER': 'task_manager',
           'PASSWORD': 'pass@2222',
           'HOST': 'localhost',
           'PORT': '5432',
       }
   }
   ```

6. Run migrations:
   ```
   python manage.py migrate
   ```

7. Create a superuser:
   ```
   python manage.py createsuperuser
   ```

8. Run the development server:
   ```
   python manage.py runserver
   ```

## API Endpoints

- `/auth/register/` - Register a new user
- `/auth/login/` - Login and receive JWT tokens
- `/auth/refresh/` - Refresh JWT token
- `/tasks/` - List all tasks (GET) or create a new task (POST)
- `/tasks/<id>/` - Retrieve, update, or delete a specific task

## Usage

1. Register a new user or login to receive your JWT token.
2. Include the token in the Authorization header for all authenticated requests:
   ```
   Authorization: Bearer <your_access_token>
   ```
3. Use the API endpoints to manage tasks.

## Filtering and Sorting

- Filter tasks by status: `/tasks/?status=pending`
- Sort tasks by due date: `/tasks/?ordering=due_date`
- Combine filters: `/tasks/?status=pending&priority=high&ordering=-due_date`

## Contributing

[Include guidelines for contributing to your project]

## License

[Specify the license under which your project is released]
