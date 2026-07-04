# CareerLens – AI Career Preparation Platform

CareerLens is a full-stack AI-powered career preparation platform that helps job seekers evaluate their resumes against target job descriptions, identify skill gaps, prepare for interviews, and generate ATS-optimized resumes. The platform leverages Large Language Models (LLMs) to deliver structured interview insights while maintaining a scalable backend architecture and secure authentication.

---

## ✨ Features

### 🔐 Authentication & Authorization
- Secure user registration and login using JWT Authentication
- Password hashing with bcrypt
- Cookie-based session management
- Token blacklisting for secure logout
- Protected routes using authentication middleware

### 📄 Resume Analysis
- Upload PDF resumes using Multer
- Extract resume text using pdf-parse
- Compare resumes with job descriptions
- Generate Job Match Score
- Identify technical and soft skill gaps with severity levels

### 🎯 AI-Powered Interview Preparation
- Personalized interview preparation roadmap
- Technical interview questions with detailed answers
- Behavioral interview questions with model responses
- Interviewer's intent for every question
- Structured JSON outputs using Gemini and Zod schema validation

### 📑 ATS Resume Generator
- Generate ATS-friendly resumes tailored to specific job descriptions
- Dynamic HTML resume generation
- PDF generation using Puppeteer
- One-click resume download

### 📊 Dashboard
- View previously generated interview reports
- Access preparation roadmaps
- Download generated resumes
- Track interview preparation history

---

# 🏗️ Architecture

```
                    +----------------------+
                    |    React Frontend    |
                    +----------+-----------+
                               |
                               |
                      Axios REST APIs
                               |
                               ▼
                  +------------------------+
                  |     Express Backend     |
                  +------------------------+
                  | Authentication          |
                  | Controllers             |
                  | Services                |
                  | Middleware              |
                  +-----------+-------------+
                              |
          +-------------------+--------------------+
          |                                        |
          ▼                                        ▼
     MongoDB                                Google Gemini
          |                                (Structured Output)
          |                                        |
          ▼                                        ▼
 Interview Reports                     Resume Analysis & Q&A
          |
          ▼
    Puppeteer PDF Generator
          |
          ▼
 ATS Resume PDF Download
```

---

# 🚀 Tech Stack

## Frontend

- React.js
- Vite
- React Router
- Axios
- SCSS
- Context API
- Custom Hooks

---

## Backend

- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT Authentication
- bcrypt
- Multer
- pdf-parse
- Puppeteer
- Cookie Parser

---

## AI

- Google Gemini API
- Google GenAI SDK
- Zod
- zod-to-json-schema

---

## Tools

- Git
- GitHub
- Postman

---

# 📂 Project Structure

```
CareerLens
│
├── Backend
│   ├── src
│   │   ├── config
│   │   ├── controllers
│   │   ├── middlewares
│   │   ├── models
│   │   ├── routes
│   │   ├── services
│   │   └── app.js
│   │
│   ├── server.js
│   └── package.json
│
└── Frontend
    ├── src
    │   ├── features
    │   │   ├── auth
    │   │   └── interview
    │   ├── style
    │   ├── App.jsx
    │   ├── app.routes.jsx
    │   ├── main.jsx
    │   └── style.scss
    │
    ├── vite.config.js
    └── package.json
```

---

# ⚙️ Installation

## Clone Repository

```bash
git clone https://github.com/yourusername/CareerLens.git

cd CareerLens
```

---

## Backend Setup

```bash
cd Backend

npm install
```

Create a `.env` file.

```env
PORT=5000

MONGO_URI=your_mongodb_connection_string

JWT_SECRET=your_jwt_secret

GOOGLE_API_KEY=your_gemini_api_key
```

Run backend

```bash
npm run dev
```

---

## Frontend Setup

```bash
cd Frontend

npm install
```

Create a `.env`

```env
VITE_API_URL=http://localhost:5000
```

Run frontend

```bash
npm run dev
```

---

# 📌 API Flow

```
User
   │
   ▼
Login/Register
   │
   ▼
JWT Authentication
   │
   ▼
Upload Resume + Job Description
   │
   ▼
PDF Parsing
   │
   ▼
Gemini Structured Analysis
   │
   ▼
Interview Report
   │
   ├── Match Score
   ├── Skill Gap Analysis
   ├── Interview Questions
   ├── Preparation Roadmap
   └── ATS Resume
   │
   ▼
MongoDB
   │
   ▼
Dashboard
```

---

# 🔄 Workflow

### 1. User Authentication

- Register/Login
- JWT generated
- Stored as HTTP-only cookie
- Protected endpoints verified using middleware

---

### 2. Resume Analysis

- Upload PDF resume
- Parse text using pdf-parse
- Read target job description
- Generate structured interview report using Gemini

---

### 3. Interview Report

Generated report contains

- Match Score
- Skill Gap Analysis
- Technical Questions
- Behavioral Questions
- Interview Roadmap

---

### 4. ATS Resume Generation

- AI rewrites resume according to job description
- Resume converted into HTML
- Puppeteer generates PDF
- User downloads ATS-ready resume

---

# 🔒 Security Features

- JWT Authentication
- Password Hashing (bcrypt)
- HTTP-only Cookies
- Token Blacklisting
- Protected Routes
- Input Validation
- Secure File Upload Handling

---

# 📈 Future Improvements

- OAuth Login (Google/GitHub)
- Resume Version Management
- Interview Performance Analytics
- Real-time Progress Tracking
- Redis Caching
- Docker Deployment
- CI/CD using GitHub Actions
- Unit & Integration Testing
- AI Voice Mock Interviews
- Email Notifications
- Interview Calendar Integration

---

# 👨‍💻 Author

**Shashank Molugu**

- LinkedIn: https://linkedin.com/in/your-profile
- GitHub: https://github.com/your-username

---

## ⭐ If you found this project useful, consider giving it a star!
