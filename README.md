# 🌐 Veris Ecosystem

## 📖 Overview

**Veris Ecosystem** is a **full-stack application** designed to power an **autonomous investigative AI agent**. It seamlessly integrates a Python/LangGraph backend with a Next.js frontend to provide an intelligent, interactive system for conducting online investigations.

The **backend** manages AI-driven data collection, verification, relationship mapping, and iterative reasoning. The **frontend** provides a modern, user-friendly interface to interact with the agent, submit queries, and visualize results such as evidence, credibility scores, and knowledge graphs.

---

## 🏗️ Project Structure

```
veris-ecosystem/
│
├── backend/       # Python + LangGraph investigative agent
│   ├── workflow/  # Core workflow nodes (collector, verifier, refiner, etc.)
│   ├── schema.py  # Pydantic models for structured data
│   ├── main.py    # Entry point (FastAPI / API server)
│   └── ...        
│
├── frontend/      # Next.js frontend application
│   ├── app/       # Pages & routes (sign-in, dashboards, etc.)
│   ├── components # Reusable React components
│   ├── lib/       # Utility libraries
│   ├── styles/    # CSS/Global styles
│   └── ...
│
└── README.md      # Documentation (this file)
```

* **Backend**: AI reasoning, data gathering, verification, and decision-making.
* **Frontend**: User interface for investigations, authentication, and visualization.

---

## ⚙️ Prerequisites

Before setting up, ensure you have:

* **Backend**:

  * Python **3.10+**
  * `pip` / `venv` (recommended)
  * API key for LLM provider (e.g., OpenAI, Anthropic, etc.)

* **Frontend**:

  * Node.js **18+**
  * Package manager: `npm`, `yarn`, `pnpm`, or `bun`

* **Optional**:

  * Docker (for containerized deployment)
  * Cloud hosting (Vercel, AWS, Heroku, etc.)

---

## 🚀 Installation

### 🔹 Backend Setup

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd <repository-directory>/backend
   ```

2. **Create a virtual environment**

   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Configure environment variables** (`.env`)

   ```
   LLM_API_KEY=<your-llm-api-key>
   SCRAPER_API_KEY=<optional-scraper-key>
   ```

---

### 🔹 Frontend Setup

1. **Navigate to frontend directory**

   ```bash
   cd <repository-directory>/frontend
   ```

2. **Install dependencies**

   ```bash
   npm install   # or yarn / pnpm / bun
   ```

3. **Configure environment variables** (`.env.local`)

   ```
   NEXT_PUBLIC_BACKEND_API_URL=http://localhost:8000
   ```

---

## ▶️ Getting Started

### Running the Backend

```bash
cd backend
uvicorn app.main:app --reload
```

The backend will be available at: **[http://localhost:8000](http://localhost:8000)**

---

### Running the Frontend

```bash
cd frontend
npm run dev
```

Open **[http://localhost:3000](http://localhost:3000)** in your browser.

---

## 🔄 Workflow Overview

The investigative agent operates in a **looped pipeline** controlled by an `AgentState` object:

1. **Collector (`collector.py`)** → Gathers evidence from online sources.
2. **Verifier (`verifier.py`)** → Evaluates credibility, assigns trust scores.
3. **Graph Node (`graph.py`)** → Builds a relationship map of entities & evidence.
4. **Refiner (`refiner.py`)** → Suggests new queries or concludes investigation.
5. **Reporter (`reporter.py`)** → Generates final structured reports (in progress).

📌 If `next_query` is set → loop continues.
📌 If `next_query = null` → investigation ends.

### Workflow Diagram

![Veris Workflow](https://github.com/user-attachments/assets/431089ef-fdae-4633-88d1-91b169919bd8)

---

## 🔧 Backend Details

* **Core Files**

  * `schema.py`: Defines data structures (Evidence, Verification Results).
  * `workflow/state.py`: Manages agent state & memory.
  * `workflow/collector.py`: Fetches online data.
  * `workflow/verifier.py`: Validates information credibility.
  * `workflow/graph.py`: Synthesizes knowledge graphs.
  * `workflow/refiner.py`: Determines next steps.
  * `workflow/reporter.py`: (In development) Generates final reports.

* **Future Enhancements**

  * Advanced graph visualizations.
  * Enhanced reporting (PDF/HTML).
  * Multi-LLM orchestration.

---

## 🎨 Frontend Details

* **Built with**: [Next.js](https://nextjs.org/)

* **Key Features**:

  * 🔑 Authentication (sign-in & user dashboard)
  * 📊 Evidence visualization (graphs, timelines)
  * 🎨 Custom UI with CSS Modules + global styles
  * ✨ Particle & animation effects (`particles.js`)

* **Custom Directories**:

  * `app/signin`: Authentication flow.
  * `app/u`: User dashboards.
  * `components/`: Modular UI components.
  * `context/`: State management with React Context.
  * `hooks/`: Reusable React hooks.
  * `lib/`: API utilities & helpers.

* **Deployment**:

  * Recommended: [Vercel](https://vercel.com/) (1-click Next.js deployment).
  * Alternative: Docker + cloud hosting.

---

## 📦 Deployment Guide

* **Frontend**: Deploy via Vercel or Netlify.
* **Backend**: Options include:

  * **FastAPI on Vercel Serverless Functions**
  * **Heroku / Render / Railway**
  * **AWS Lambda + API Gateway**
  * **Docker container** (for Kubernetes/VM deployments)

---


## 📜 License

This project is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.

---
