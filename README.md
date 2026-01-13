# Marketplace Platform

A robust, full-stack marketplace application built with FastAPI (Backend) and React/Vite (Frontend). This platform facilitates user engagement through project management, transactions, and reviews.

## 🚀 Features

### Backend (FastAPI)
- **Modular Architecture**: Organized by feature modules (User, Project, Wallet, Payment, etc.) for scalability.
- **Authentication**: Secure user registration and login system.
- **Project Management**: Create, update, and manage project listings.
- **Wallet System**: Digital wallet functionality for managing user funds.
- **Purchases & Payments**: Secure transaction processing (integrated with Stripe).
- **Reviews**: System for user feedback and ratings.
- **Database**: PostgreSQL with Async/Await support and Alembic for migrations.

### Frontend (React + Vite)
- **Modern UI**: Built with React 19 and styled using Tailwind CSS.
- **State Management**: Utilizes Redux Toolkit for efficient global state handling.
- **Animations**: Smooth UI transitions powered by Framer Motion.
- **Routing**: Client-side routing with React Router.

## 📂 Project Structure

```bash
FsstApi/
├── app/                    # Backend API Source
│   ├── core/               # Core configurations and settings
│   ├── modules/            # Feature-specific modules
│   │   ├── user/           # Authentication & User profiles
│   │   ├── project/        # Project management
│   │   ├── wallet/         # Wallet logic
│   │   ├── payment/        # Payment processing
│   │   └── ...
│   └── main.py             # Application entry point
├── frontend/               # Frontend Application
│   ├── src/                # React source code
│   ├── package.json        # Frontend dependencies
│   └── vite.config.ts      # Vite configuration
├── alembic/                # Database migrations
├── docker-compose.yml      # Docker orchestration
└── DockerFile              # Backend Docker image definition
```

## 🛠️ Installation & Setup

### Prerequisites
- **Docker & Docker Compose** (Recommended)
- OR **Python 3.11+**, **Node.js 18+**, and **PostgreSQL**

### Option 1: Using Docker (Recommended)

1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    cd FsstApi
    ```

2.  **Start the services:**
    ```bash
    docker-compose up --build
    ```
    This will start both the PostgreSQL database and the FastAPI backend.
    
    - Backend API: `http://localhost:8000`
    - API Documentation: `http://localhost:8000/docs`

3.  **Run the Frontend:**
    Open a new terminal:
    ```bash
    cd frontend
    npm install
    npm run dev
    ```
    - Frontend: `http://localhost:5173` (typically)

### Option 2: Manual Setup

#### Backend
1.  **Set up the environment:**
    Ensure you have a PostgreSQL database running and update the connection strings in your environment variables.

2.  **Install dependencies:**
    ```bash
    # Navigate to root
    pip install -r requirements.txt
    ```

3.  **Run Migrations:**
    ```bash
    alembic upgrade head
    ```

4.  **Start the Server:**
    ```bash
    uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload
    ```

#### Frontend
1.  **Navigate to the frontend directory:**
    ```bash
    cd frontend
    ```

2.  **Install details:**
    ```bash
    npm install
    ```

3.  **Start Development Server:**
    ```bash
    npm run dev
    ```

## 🔧 Environment Variables

Make sure to configure the necessary environment variables. See `docker-compose.yml` for required keys like:
- `DATABASE_URL_SYNC` / `DATABASE_URL_ASYNC`
- `SECRET_KEY`
- `STRIPE_SECRET_KEY`
- `STRIPE_WEBHOOK_SECRET`
