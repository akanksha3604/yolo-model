# 🌿 Dual Model Detection (AI-Archaeology)

This package implements a dual-model detection system, running a **FastAPI** backend for image processing and a **Vite React** frontend for the user interface. It is designed to run both servers simultaneously from a single terminal command.

---

## ✨ Features

* **Dual Models:** Runs two separate YOLO models (YOLOv11 for Soil and YOLOv8 for Vegetation).
* **Single-Terminal Runner:** Uses a Python helper script (`run_all.py`) to manage both the backend (Uvicorn) and frontend (Vite) development servers.
* **Server-Side Preprocessing:** Backend automatically resizes images to the specific target size for each model (640x640 for Soil, 1024x1024 for Vegetation).
* **API:** Annotated images are saved to the `backend/outputs` directory and served via a static endpoint.

---

## 🛠️ Prerequisites

Ensure the following tools are installed and accessible in your system's PATH:

* **Python:** Version **3.8+**
* **Node.js & npm:** Required for the React frontend.
* **Trained Models:** You must place your trained YOLO model files inside the `backend/models/` directory with the exact following names:
    * Soil Model (YOLOv11): `soil_yolo11_best.pt`
    * Vegetation Model (YOLOv8): `vegetation_model2_yolov8s_finetune_best.pt`

---

## 🚀 Setup & Installation

Follow these steps from the project root directory:

### 1. Backend Setup (Python)

Navigate to the `backend` directory, create a virtual environment, and install the necessary dependencies (FastAPI, Uvicorn, Ultralytics, etc.).

| Step | Command (macOS / Linux) | Command (Windows) |
| :--- | :--- | :--- |
| **Navigate** | `cd backend` | `cd backend` |
| **Create venv** | `python -m venv venv` | `python -m venv venv` |
| **Activate venv** | `source venv/bin/activate` | `venv\Scripts\activate` |
| **Install Deps** | `pip install -r requirements.txt` | `pip install -r requirements.txt` |
| **Return to Root** | `cd ..` | `cd ..` |

### 2. Frontend Setup (Node.js)

Navigate to the `frontend` directory and install the Node.js packages (React, Vite, Axios, etc.).

| Step | Command |
| :--- | :--- |
| **Navigate** | `cd frontend` |
| **Install Deps** | `npm install` |
| **Return to Root** | `cd ..` |

---

## 🏃 Running the Application

From the **project root** directory, execute the main helper script:

```bash
python run_all.py