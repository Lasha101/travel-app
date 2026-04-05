# Backend API

The backend service for the Passport Management platform. It handles secure user authentication, database operations, and asynchronous background tasks for OCR processing.

## Core Features
- **FastAPI Framework:** High-performance REST API.
- **Google Cloud Vision OCR:** Asynchronous document parsing and data extraction.
- **Server-Sent Events (SSE):** Real-time progress updates to the frontend for long-running OCR tasks.
- **PostgreSQL via SQLAlchemy:** Relational data management and automated schema generation.
- **Role-Based Access Control (RBAC):** JWT authentication with distinct User and Admin privileges.

## Local Setup
1. Create a virtual environment: `python -m venv venv && source venv/bin/activate`
2. Install dependencies: `pip install -r requirements.txt`
3. Configure your `.env` file (Database URL, Google Cloud Credentials, JWT Secret).
4. Run the server: `uvicorn main:app --reload`