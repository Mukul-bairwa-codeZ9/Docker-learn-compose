# 🐳 Docker Learn Compose

## Full-Stack Dockerized MERN Application

This project is a structured boilerplate for a **React (Frontend)**, **Node.js (Backend)**, and **MongoDB (Database)** application, fully orchestrated using Docker Compose.

It features separate environments for:
- **Development** (with Hot Module Replacement)
- **Production** (using Nginx and multi-stage builds)

---

## 📂 Project Structure

The project is organized into three main parts:
root/
│
├── docker-compose.yml
├── docker-compose.dev.yml
├── docker-compose.prod.yml
├── .env
│
├── backend/
│   └── Docker-learn-node-app-
│
└── frontend/
└── Docker-learn-react-app-
- **Root** → Orchestration layer (Docker Compose + environment config)- **Backend** → Node.js/Express API- **Frontend** → React (Vite) app---## 🚀 Getting Started### Prerequisites- Docker Desktop installed and running- A `.env` file in the root directory (see below)---### Installation1. Clone the root repository:```powershellgit clone <root-repo-url>cd <root-folder>


Clone the sub-repositories:


git clone <backend-repo-url> backend/Docker-learn-node-app-git clone <frontend-repo-url> frontend/Docker-learn-react-app-

🛠 Usage
This project uses Docker Compose overrides to switch between environments.

👨‍💻 Development Mode
Includes:


Nodemon (backend)


Vite HMR (frontend)


Local code syncs into containers in real time.
docker compose -f docker-compose.yml -f docker-compose.dev.yml up --build
Access:


Frontend → http://localhost:5173


Backend → http://localhost:3000


MongoDB → localhost:27017



🏗 Production Mode
Uses:


Multi-stage builds


Nginx for frontend serving


docker compose -f docker-compose.yml -f docker-compose.prod.yml up --build
Access:


Frontend → http://localhost (Port 80)


Backend → http://localhost:3000



🔑 Environment Variables
Create a .env file in the root directory:
MONGO_USERNAME=rootMONGO_PASSWORD=your_secure_passwordMONGO_URI=mongodb://root:your_secure_password@db:27017/myapp?authSource=admin
⚠️ Important: Never commit your .env file to version control.

📦 Container Summary
ServiceContainer NamePurposedbmongo_dbMongoDB 7.0 Databasebackendnode_apiExpress API (Node 20 Alpine)frontendreact_appReact (Dev) / Nginx (Prod)

🧹 Useful Commands
# Stop servicesdocker compose down# Stop and remove volumes (wipe data)docker compose down -v# View logsdocker compose logs -f# Access backend shelldocker compose exec backend sh

💡 Tip (Windows Users)
Since Windows does not include make by default, use the provided PowerShell script:
.\run.ps1 dev
This provides shorter aliases for common commands.

📌 Notes


Development mode is optimized for rapid iteration


Production mode is optimized for performance and security


Ensure Docker Desktop is running before executing commands

