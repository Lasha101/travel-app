# Gestionnaire de Voyages (Travel & Passport Manager)

A robust, full-stack web application designed to automate the extraction and management of passport data using Optical Character Recognition (OCR). Built with a modern FastAPI backend and a responsive React frontend, this app features real-time OCR processing, user management, and seamless data exports.

## Features

* **Automated OCR Extraction:** Upload passport images or PDFs and automatically extract Machine Readable Zone (MRZ) data (Name, Passport Number, Nationality, Expiration, etc.) using Google Cloud Vision.
* **Real-Time Progress Tracking:** View live status updates of your OCR extraction jobs via Server-Sent Events (SSE).
* **User & Credit Management:** Role-based access control (Admin vs. User). Admins can manage users, generate invitation links, and allocate OCR page credits.
* **Data Export:** Filter and download your passport and voyage data as CSV files.
* **Bulk Operations:** Edit destinations or delete multiple passports at once.
* **Fully Dockerized:** Easy deployment using Docker, Docker Compose, and Nginx. Includes a GitHub Actions pipeline for AWS EC2 deployments.

## Tech Stack

* **Frontend:** React (Vite), native CSS.
* **Backend:** Python, FastAPI, SQLAlchemy, Pydantic.
* **Database:** PostgreSQL (with a local SQLite fallback for dev).
* **Authentication:** JWT (JSON Web Tokens) & bcrypt.
* **Cloud Services:** Google Cloud Vision API, Google Cloud Storage (GCS).
* **Infrastructure:** Docker, Docker Compose, Nginx, GitHub Actions.

## Prerequisites

Before you begin, ensure you have the following installed and set up:
* [Docker](https://www.docker.com/) and Docker Compose.
* A Google Cloud Platform (GCP) account.
    * Enable the **Cloud Vision API**.
    * Create two **Google Cloud Storage (GCS) Buckets** (one for input, one for output).
    * Generate a Service Account JSON Key with permissions to use Vision API and read/write to your GCS buckets.

## Environment Variables

Create a `.env` file in the root directory and configure the following variables. These are strictly required for the database, authentication, and Google Cloud integrations to function properly:

```env
# Database Configuration
POSTGRES_USER=myuser
POSTGRES_PASSWORD=mypassword
POSTGRES_DB=travel_db

# Security
SECRET_KEY=your_super_secret_jwt_key
ACCESS_TOKEN_EXPIRE_MINUTES=30
ADMIN_PASSWORD=your_secure_admin_password

# Google Cloud Configuration
GCS_INPUT_BUCKET=your-gcs-input-bucket-name
GCS_OUTPUT_BUCKET=your-gcs-output-bucket-name
# Minify your GCP Service Account JSON into a single line string
GCP_CREDS_JSON='{"type": "service_account", "project_id": "...", ...}'