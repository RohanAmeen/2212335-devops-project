# DevOps Final Project - Rohan Ameen

**Registration Number:** 2212335

## Project Overview
A containerised FastAPI microservice with a PostgreSQL database, deployed automatically to AWS EC2 using GitHub Actions CI/CD.

## Architecture
- **Web Service:** FastAPI + Uvicorn (Port 8000)
- **Database:** PostgreSQL 15 (Port 5432) with persistent named volume
- **CI Pipeline:** GitHub Actions (Lint + Test on every push/PR)
- **CD Pipeline:** GitHub Actions (Auto-deploy to EC2 on push to main)
- **Cloud Server:** AWS EC2 t2.micro (Ubuntu)

## API Endpoints
- `GET /health` - Health check and DB status
- `POST /students` - Create a new student record
- `GET /students` - Get all student records
- `GET /students/{reg_no}` - Get a specific student by registration number

## Setup Instructions

### Local Development
```bash
# 1. Clone the repository
git clone https://github.com/RohanAmeen/2212335-devops-project.git
cd 2212335-devops-project

# 2. Create .env file
cp .env.example .env

# 3. Run with Docker Compose
docker compose up --build

# 4. Access the app
# http://localhost:8000/health

### Production (EC2)
# Automatically deployed via GitHub Actions CD pipeline when code is pushed to the main branch
