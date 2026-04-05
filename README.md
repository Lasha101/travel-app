# Passport & Travel Management Platform (MVP)

A full-stack monorepo web application designed to manage passports and travel destinations, featuring automated data extraction from documents using OCR. 

**Note on Development:** This project was built primarily leveraging prompt engineering to rapidly architect, develop, and deploy a robust Minimum Viable Product.

**Live Deployment:** The application is currently hosted and running on AWS EC2. It is deployed to production to be accessible to real users, allowing me to gather actual user feedback, maintain the system, and guide further feature development.

## Architecture & Tech Stack
- **Frontend:** React (Vite)
- **Backend:** Python (FastAPI)
- **Database:** PostgreSQL
- **Cloud/AI:** Google Cloud Vision API (OCR), Google Cloud Storage
- **Infrastructure:** Docker, Docker Compose, Nginx, GitHub Actions (CI/CD to AWS EC2)

## Repository Structure
- `/frontend`: React user interface.
- `/backend`: FastAPI backend and background workers.
- `docker-compose.yml`: Local and production container orchestration.
- `.github/workflows/deploy.yml`: Automated deployment pipeline.