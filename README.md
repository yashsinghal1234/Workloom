# 🚀 WorkLoom

WorkLoom is a freelance marketplace platform designed to connect clients with the ideal freelancers using an intelligent pairing system. By automating proposals and optimizing pricing strategies, WorkLoom ensures seamless collaboration and efficient task management.

## 📋 Table of Contents
- [Description](#-description)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Architecture](#-project-architecture)
- [Installation & Setup](#-installation--setup)
- [Docker Deployment](#-docker-deployment)
- [CI/CD Workflow](#-cicd-workflow)
- [Environment Configuration](#-environment-configuration)
- [Usage](#-usage)
- [Contributors](#-contributors)

---

## 📖 Description
WorkLoom modernizes the traditional freelance platform experience by providing an automated and data-driven approach to matching talent with projects. With a React-based interactive frontend and a secure Node/Express backend powered by MongoDB, the platform focuses on reducing administrative overhead for freelancers via automated PDF parsing for proposal generation and intelligent market-fair pricing.

## ✨ Features
- **Client Project Posting:** Clean and interactive portal for clients to post, edit, and organize project requirements.
- **Freelancer Matching System:** Advanced suggestion engine matching ideal candidates based on their skill sets.
- **Intelligent Pricing Suggestion:** Evaluates current variables to suggest fair and competitive rates automatically.
- **Automated Proposal Generation:** Leverages seamless document mapping (`pdf-parse`, `mammoth`) to auto-create and format professional freelance proposals.
- **Secure Authentication:** Implements strict client-freelancer isolation through JWT and `bcryptjs`.
- **Dockerized Environment:** Ensures reliable, reproducible container builds across both development and production.
- **Automated CI/CD Pipeline:** Fully configured GitHub Actions integrating automated testing, Docker container builds, and deployment workflows.

## 🛠️ Tech Stack
### **Frontend**
- **React 19** & **Vite**
- **React Router v6**
- **React Hook Form** + **Zod** (Client-side validation)
- **Nginx** (Optimized static serving via Docker)

### **Backend**
- **Node.js** & **Express**
- **MongoDB** via Mongoose (NoSQL database)
- **JSON Web Tokens (JWT)** & **Bcrypt.js** (Security and Authentication)
- **Multer**, **PDF-Parse**, **Mammoth** (Document processing)
- **Nodemailer** (Email communications)

### **DevOps & Deployment**
- **Docker** & **Docker Compose**
- **GitHub Actions** (CI/CD workflows and Docker registries)

---

## 📁 Project Architecture
```text
WorkLoom/
├── .github/workflows/      # CI/CD (GitHub Actions, SSH, GHCR)
├── src/                    # Vite + React Frontend Config
│   ├── components/         # Reusable React components
│   ├── pages/              # Application views
│   └── lib/                # Utility frontend scripts
├── server/                 # Express REST API Backend
│   ├── src/
│   │   ├── controllers/    # API Request Handlers
│   │   ├── models/         # Mongoose User/Project Schemas
│   │   ├── routes/         # Express Route Definitions
│   │   ├── middleware/     # Auth and error handlers
│   │   ├── services/       # PDF and Matching Services
│   │   └── utils/          # Helper utilities
├── public/                 # Static Frontend assets
├── Dockerfile              # Nginx web server build setup
└── server/Dockerfile       # Backend Node environment build setup
```

---

## ⚙️ Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Aditya010305/WorkLoom.git
   cd WorkLoom
   ```

2. **Frontend Setup:**
   ```bash
   npm install
   npm run dev
   ```

3. **Backend Setup:**
   ```bash
   cd server
   npm install
   npm run dev
   ```
   *(Backend starts on local port 4000)*

---

## 🐳 Docker Deployment

To launch the full application in an isolated environment using Docker Compose:

1. Ensure the Docker engine is running on your host machine.
2. Launch both the web and API components:
   ```bash
   docker-compose up --build
   ```
3. To stop and securely remove containers:
   ```bash
   docker-compose down
   ```

---

## 🔄 CI/CD Workflow

WorkLoom utilizes **GitHub Actions** to enforce continuous integration and structured deployment pipelines:
- **Continuous Integration (CI):** Every push to the `main` branch triggers an automated workflow that runs code linting (`npm run lint`), ensuring standardization, and builds the production frontend application.
- **Docker Registries:** The pipeline automatically packages both the frontend (using Nginx) and backend (Node.js) applications into optimized Docker images. These images are verified and pushed to the GitHub Container Registry (GHCR).
- **Deployment Strategy:** Platform deployment is managed securely via SSH. Upon successful registry pushes, the target servers use Docker Compose to pull the newest configured images and restart seamlessly, ensuring rolling updates with no critical downtime.

---

## 🔐 Environment Configuration

Create a `.env` file within the `./server/` directory and configure the environment-specific variables. Ensure that no actual credentials are ever pushed to version control.

```env
PORT=your_port_number
DATABASE_URL=your_mongodb_connection_uri
JWT_SECRET=your_secure_authentication_key
EMAIL_HOST=your_smtp_provider
EMAIL_USER=your_smtp_username
EMAIL_PASS=your_smtp_password
```

---

## 🚀 Usage

1. Configure the `.env` variables and boot the platform using either Docker Compose or local Node run commands.
2. Access the frontend interface at `http://localhost:5173`.
3. Account initiation begins with a unified registration format. **Clients** can define gig assignments while **Freelancers** can attach credentials to be automatically reviewed for role suitability.

---

## 🤝 Contributors

## 🤝 Contributors

<table align="center">
  <tr>
    <td align="center" width="150">
      <a href="https://github.com/Aditya010305">
        <img src="https://github.com/Aditya010305.png" width="110px;" style="border-radius:50%;" alt="Aditya"/><br />
        <sub><b>Aditya Pratap Singh</b></sub>
      </a><br />
      <sub>@Aditya010305</sub>
    </td>
    <td align="center" width="150">
      <a href="https://github.com/Ajeetshukla1">
        <img src="https://github.com/Ajeetshukla1.png" width="110px;" style="border-radius:50%;" alt="Ajeet"/><br />
        <sub><b>Ajeet Shukla</b></sub>
      </a><br />
      <sub>@Ajeetshukla1</sub>
    </td>
    <td align="center" width="150">
      <a href="https://github.com/yashsinghal1234">
        <img src="https://github.com/yashsinghal1234.png" width="110px;" style="border-radius:50%;" alt="Yash"/><br />
        <sub><b>Yash Singhal</b></sub>
      </a><br />
      <sub>@yashsinghal1234</sub>
    </td>
    <td align="center" width="150">
      <a href="https://github.com/Nova-022005">
        <img src="https://github.com/Nova-022005.png" width="110px;" style="border-radius:50%;" alt="Saurav"/><br />
        <sub><b>Saurav Singh</b></sub>
      </a><br />
      <sub>@Nova-022005</sub>
    </td>
  </tr>
</table>