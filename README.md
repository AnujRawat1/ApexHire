# ApexHire

> **AI-Powered Career & Recruitment Platform**  
> Comprehensive resume analysis, ATS optimization, AI mock interviews, and career mentoring.

---

## Architecture Overview

ApexHire is built using a modern microservices architecture across three dedicated repositories:

| Component | Service / Repository | Technology Stack | Description |
| :--- | :--- | :--- | :--- |
| **Frontend** | [apex-resume-frontend-4b0390e9](https://github.com/AnujRawat1/apex-resume-frontend-4b0390e9) | React 19, Vite, TanStack Router, Tailwind CSS | Interactive user interface, real-time PDF viewer, and report dashboard. |
| **Backend** | [ApexHire-Backend](https://github.com/AnujRawat1/ApexHire-Backend) | Spring Boot 3, Java 21, Spring Security, MongoDB | Core API gateway, JWT/OAuth2 authentication, file storage, and data management. |
| **AI Service** | [ApexHire-AI](https://github.com/AnujRawat1/ApexHire-AI) | Python, FastAPI, LangGraph / LangChain, Gemini API | Multi-agent resume parser, ATS evaluation engine, and scoring models. |

---

## Getting Started

### 1. Clone with Submodules

To clone the entire project including all three sub-repositories:

```bash
git clone --recurse-submodules https://github.com/AnujRawat1/ApexHire.git
cd ApexHire
```

*(If you already cloned without `--recurse-submodules`, run `git submodule update --init --recursive`)*

---

### 2. Prerequisites

- **Java**: JDK 21+
- **Python**: Python 3.11+
- **Node.js**: Node.js 20+ & npm / bun
- **Database**: MongoDB running on `mongodb://localhost:27017`

---

### 3. Running the Services

#### Step A: Start the Python AI Backend
```bash
cd ApexHire_PythonBackend

# Create and activate virtual environment
python -m venv .venv
.venv\Scripts\activate       # On Windows
# source .venv/bin/activate  # On macOS/Linux

# Install dependencies and run
pip install -r requirements.txt
uvicorn app.main:app --port 8000 --reload
```
*Runs on: `http://localhost:8000`*

#### Step B: Start the Spring Boot Backend
```bash
cd ../ApexHire

# Run with Maven wrapper
./mvnw spring-boot:run
```
*Runs on: `http://localhost:9000`*

#### Step C: Start the React Frontend
```bash
cd ../apex-resume-frontend-4b0390e9

# Install dependencies and start dev server
npm install
npm run dev
```
*Runs on: `http://localhost:5173`*

---

## Project Highlights

- **AI Resume Review & Scoring**: Instant scoring across ATS compatibility, skills alignment, keywords, and job description match.
- **Side-by-Side PDF Viewer**: In-browser PDF streaming with interactive score breakdowns and actionable rewrite recommendations.
- **Enterprise Security**: Token-based authentication with refresh tokens, password reset flows, and Google/GitHub OAuth2.
