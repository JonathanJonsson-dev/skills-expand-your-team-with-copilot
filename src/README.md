# Mergington High School Activities

A comprehensive web application for managing extracurricular activities at Mergington High School. The system provides an intuitive interface for viewing activities and allows teachers to manage student registrations with proper authentication and role-based access control.

## Features

### Student Features
- Browse all available extracurricular activities with detailed information
- Search activities by name using the search box
- Filter activities by:
  - Day of the week (Monday through Sunday)
  - Time slot (Before School, After School, Weekend)
  - Category (automatically detected from activity types)
- View activity schedules, descriptions, and current participant counts
- Responsive design that works on desktop and mobile devices

### Teacher Features  
- Secure authentication system with role-based access
- Register students for activities via email
- Unregister students from activities
- View all activity participant lists
- Session management with automatic validation

### System Features
- Real-time activity filtering and search
- Persistent data storage with MongoDB
- RESTful API architecture
- Modern responsive web interface
- Comprehensive error handling and validation

## Available Activities

The system comes pre-loaded with 13 diverse extracurricular activities:

**Academic Activities:**
- Chess Club (Mondays & Fridays, 3:15-4:45 PM)
- Programming Class (Tuesdays & Thursdays, 7:00-8:00 AM)  
- Math Club (Tuesdays, 7:15-8:00 AM)
- Debate Team (Fridays, 3:30-5:30 PM)
- Science Olympiad (Saturdays, 1:00-4:00 PM)

**Sports Activities:**
- Morning Fitness (Mon/Wed/Fri, 6:30-7:45 AM)
- Soccer Team (Tuesdays & Thursdays, 3:30-5:30 PM)
- Basketball Team (Wednesdays & Fridays, 3:15-5:00 PM)

**Arts & Creative Activities:**
- Art Club (Thursdays, 3:15-5:00 PM)
- Drama Club (Mondays & Wednesdays, 3:30-5:30 PM)

**Special Interest Activities:**
- Weekend Robotics Workshop (Saturdays, 10:00 AM-2:00 PM)
- Sunday Chess Tournament (Sundays, 2:00-5:00 PM)
- Manga Maniacs (Tuesdays, 7:00-9:00 PM)

## Technology Stack

**Backend:**
- FastAPI - Modern, fast web framework for building APIs
- MongoDB - Document database for persistent data storage
- Uvicorn - ASGI server for running the FastAPI application
- Argon2 - Secure password hashing
- PyMongo - MongoDB driver for Python

**Frontend:**
- HTML5 - Semantic markup structure
- CSS3 - Modern styling with responsive design
- Vanilla JavaScript - Client-side functionality and API interaction

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/` | Redirects to the main application interface |
| `GET` | `/activities` | Get all activities with optional filtering by day, start_time, end_time |
| `GET` | `/activities/days` | Get list of all days that have activities scheduled |
| `POST` | `/activities/{activity_name}/signup` | Register a student for an activity (requires teacher authentication) |
| `POST` | `/activities/{activity_name}/unregister` | Remove a student from an activity (requires teacher authentication) |
| `POST` | `/auth/login` | Teacher login with username and password |
| `GET` | `/auth/check-session` | Validate teacher session by username |
| `GET` | `/docs` | Interactive API documentation (Swagger UI) |
| `GET` | `/redoc` | Alternative API documentation (ReDoc) |

## Teacher Accounts

The system includes pre-configured teacher accounts for testing:

| Username | Display Name | Password | Role |
|----------|--------------|----------|------|
| `mrodriguez` | Ms. Rodriguez | `art123` | teacher |
| `mchen` | Mr. Chen | `chess456` | teacher |
| `principal` | Principal Martinez | `admin789` | admin |

## Development Guide

For detailed setup and development instructions, please refer to our [Development Guide](../docs/how-to-develop.md).

## Database

The application uses MongoDB for persistent data storage. The database is automatically initialized with sample activities and teacher accounts when the application starts for the first time. Data includes:

- **Activities Collection**: Stores activity details, schedules, participant lists, and metadata
- **Teachers Collection**: Stores teacher credentials, display names, and role information

All passwords are securely hashed using Argon2 before storage.
