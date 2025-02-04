# AI Project

This repository contains a structured AI project designed for development, training, and deployment of machine learning models. The folder structure follows best practices to ensure modularity, scalability, and ease of deployment.

## Project Structure

```
AI_Project/
│── src/                        # Source code directory
│   ├── data/                   # Data processing scripts
│   │   ├── preprocess.py        # Data preprocessing script
│   │   ├── loader.py            # Custom data loader
│   ├── models/                 # Model architectures and training scripts
│   │   ├── Load/
            ├── train.py         # training file for load energy
            ├── evaluate.py      # evaluating file for load energy
        |── Wind/
            ├── train.py         # training file for wind energy
            ├── evaluate.py      # evaluating file for wind energy

│   ├── utils/                  # Utility functions
│   │   ├── exceptions.py        # Custom Exceptions
│   │   ├── logger.py            # Logging utilities
│   ├── deployment/              # Deployment-related files
│   │   ├── api.py               # FastAPI/Flask app for serving the model
│   │   ├── Dockerfile           # Docker setup for deployment
│── notebooks/                   # Jupyter notebooks for experimentation
│── data/                        # Data storage 
│   ├──raw_data/                  
│   ├── perprocessed_data/                   

│── models/                      # Saved models and checkpoints
│── logs/                        # Training and deployment logs
│── tests/                       # Unit and integration tests
│── config/                      # Configuration files
│── scripts/                     # Automation scripts
│── docs/                        # Documentation
│── requirements.txt             # Project dependencies
│── .gitignore                    # Git ignore file (exclude logs, data, models, etc.)
│── docker-compose.yml            # Docker Compose file for multi-container deployment
│── README.md                     # Project description and usage instructions
```

## Folder Descriptions

### `src/`
This is the core directory containing all source code for data processing, model building, and utilities.
- **`data/`**: Scripts for handling and preprocessing datasets.
- **`models/`**: Model architecture definitions, training, evaluation, and inference scripts.
- **`utils/`**: Helper functions for logging, configuration, and metrics.
- **`deployment/`**: API and deployment files for serving the model using Flask/FastAPI.

### `notebooks/`
Contains Jupyter notebooks used for data exploration, experimentation, and model training/testing.

### `data/`
Stores raw and processed datasets. (Raw data should not be pushed to Git for privacy and storage reasons.)

### `models/`
Contains trained models, checkpoints, and exported versions for deployment (e.g., `.pth`, `.onnx`, `.tflite`).

### `logs/`
Stores logs generated during model training and deployment for debugging and monitoring.

### `tests/`
Unit and integration tests to ensure the reliability of data processing, models, and API endpoints.

### `config/`
Configuration files (`.yaml` or `.json`) for hyperparameters, environment settings, and deployment configurations.

### `scripts/`
Shell scripts for automating common tasks such as training, evaluation, and deployment.

### `docs/`
Documentation files describing project setup, API usage, and other important details.

### Root Files
- **`requirements.txt`**: Lists all dependencies needed to run the project.
- **`setup.py`**: Allows for package installation if needed.
- **`.gitignore`**: Excludes unnecessary files (e.g., logs, datasets, compiled binaries) from version control.
- **`docker-compose.yml`**: Defines multi-container deployment settings.
- **`README.md`**: This file, providing an overview of the project.

## Getting Started

### 1. Clone the repository
```sh
git clone https://github.com/your-repo-name.git
cd AI_Project
```

### 2. Set up a virtual environment
```sh
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```

### 3. Install dependencies
```sh
pip install -r requirements.txt
```

### 4. Run training
```sh
python src/models/model_x/train.py
```

### 5. Serve the model via API
```sh
uvicorn src.deployment.api:app --host 0.0.0.0 --port 8000
```

### 6. Run tests
```sh
pytest tests/
```

## Deployment
For deployment, use Docker:
```sh
docker build -t ai_project .
docker run -p 8000:8000 ai_project
```


---

