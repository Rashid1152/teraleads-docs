# AI-Powered Dental Clinic Dashboard

A full-stack web application for dental clinics, featuring patient management and an AI-powered assistant. Built with Django (backend), React (frontend), PostgreSQL, and OpenAI integration. Fully dockerized for easy deployment.

---

## Features
- **Patient Management:** CRUD operations for patient records
- **AI Chatbot:** Ask dental/clinic-related questions and get smart AI answers
- **JWT Authentication:** Secure login and protected API endpoints
- **Modern UI:** Built with React and Material UI
- **Dockerized:** Easy to run locally or deploy

---

## Tech Stack
- **Backend:** Django, Django REST Framework, PostgreSQL, SimpleJWT, OpenAI
- **Frontend:** React, Material UI, Axios
- **Deployment:** Docker, Docker Compose

---

## Setup Instructions

### 1. Prerequisites
- [Docker](https://www.docker.com/products/docker-desktop) & Docker Compose
- OpenAI API key (for chatbot)
- **Note:** The frontend was developed using npm version 10.9.2 (for reference)

### 2. Clone the Repository
```sh
git clone <your-repo-url>
cd <repo-directory>
```

### 3. Set Environment Variables
Create a `.env` file in the `backend/` root directory with the following content:
```
# OpenAI API Key (optional for AI chatbot)
OPENAI_API_KEY=sk-...

# PostgreSQL credentials
POSTGRES_DB=teraleads_db
POSTGRES_USER=teraleads_user
POSTGRES_PASSWORD=teraleads_pass
POSTGRES_HOST=db
POSTGRES_PORT=5432
```
- If `OPENAI_API_KEY` is **not set**, the chatbot will return a dummy reply instead of a real AI answer.

### 4. Build and Run with Docker Compose
```sh
docker-compose up --build
```
- Frontend: [http://localhost:3000](http://localhost:3000)
- Backend: [http://localhost:8000](http://localhost:8000)
- Admin: [http://localhost:8000/admin](http://localhost:8000/admin)

### 5. Create a Superuser (for login)
```sh
docker-compose exec backend python manage.py createsuperuser
```

---

## API Documentation

### Auth
- `POST /api/token/` — Obtain JWT token (username, password)
- `POST /api/token/refresh/` — Refresh JWT token

### Patients
- `GET /api/patients/` — List all patients
- `POST /api/patients/` — Create a new patient
- `GET /api/patients/{id}/` — Retrieve a patient
- `PUT /api/patients/{id}/` — Update a patient
- `DELETE /api/patients/{id}/` — Delete a patient

### Chatbot
- `POST /api/chatbot/` — Ask a question
  - Body: `{ "question": "Your question here" }`
  - Response: `{ "reply": "AI answer" }`

---

## Assumptions & Limitations
- **OpenAI API key is optional:** If not set, chatbot will return a dummy reply.
- Not production-hardened (uses Django dev server, no HTTPS, etc.)
- CORS is enabled for local development
- No user registration (admin creates users)
- Error handling is basic for demo purposes

---

## Contact
For questions or support, contact [rashid.aziz1152@gmail.com] 

---

## Clinic Dashboard Screenshot
![image](https://github.com/user-attachments/assets/286a0b75-ccab-4b19-a5e5-fe9744706f34)
