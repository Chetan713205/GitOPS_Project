# MLOps Project 9: Smart Manufacturing

## Overview

This is an MLOps project focused on smart manufacturing, implementing end-to-end machine learning pipelines for data processing, model training, and deployment. The project includes a Flask web application for serving predictions, containerization with Docker, CI/CD with Jenkins, and Kubernetes manifests for deployment.

## Features

- **Data Processing**: Automated pipeline for ingesting and preprocessing manufacturing data.
- **Model Training**: Machine learning models trained on processed data with logging and artifact management.
- **Web Application**: Flask-based API for model inference and visualization.
- **Containerization**: Docker setup for easy deployment.
- **CI/CD**: Jenkins pipeline for automated testing and deployment.
- **Kubernetes Deployment**: Manifests for deploying to Kubernetes clusters.

## Project Structure

```
.
├── application.py              # Main Flask application
├── Dockerfile                  # Docker container configuration
├── Jenkinsfile                 # CI/CD pipeline configuration
├── requirements.txt            # Python dependencies
├── setup.py                    # Package setup
├── artifacts/                  # Model artifacts and data
│   ├── models/                 # Trained models
│   ├── processed/              # Processed data
│   └── raw/                    # Raw data (e.g., data.csv)
├── logs/                       # Application logs
├── manifests/                  # Kubernetes manifests
│   ├── deployment.yaml         # Deployment configuration
│   └── service.yaml            # Service configuration
├── myenv/                      # Python virtual environment
├── notebook/                   # Jupyter notebooks
│   └── notebook.ipynb          # Exploratory data analysis
├── pipeline/                   # ML pipeline code
│   ├── __init__.py
│   └── training_pipeline.py    # Model training pipeline
├── src/                        # Source code
│   ├── __init__.py
│   ├── custom_exception.py     # Custom exceptions
│   ├── data_processing.py      # Data processing utilities
│   ├── logger.py               # Logging utilities
│   └── model_training.py       # Model training logic
├── static/                     # Static web assets
│   └── style.css               # CSS styles
├── templates/                  # Flask templates
│   └── index.html              # Web interface
└── MLOPS_PROJECT_9.egg-info/    # Package metadata
```

## Installation

### Prerequisites

- Python 3.8+
- Docker (for containerization)
- Kubernetes (for deployment, optional)
- Jenkins (for CI/CD, optional)

### Setup

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd mlops-project-9
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv myenv
   # On Windows:
   myenv\Scripts\activate
   # On macOS/Linux:
   source myenv/bin/activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. (Optional) Install the package locally:
   ```bash
   pip install -e .
   ```

## Usage

### Running the Flask Application

1. Ensure the virtual environment is activated.
2. Run the application:
   ```bash
   python application.py
   ```
3. Open your browser and navigate to `http://localhost:5000`.

### Training the Model

1. Run the training pipeline:
   ```bash
   python pipeline/training_pipeline.py
   ```
2. Check the `artifacts/models/` directory for trained models and `logs/` for training logs.

### Using Docker

1. Build the Docker image:
   ```bash
   docker build -t mlops-project-9 .
   ```

2. Run the container:
   ```bash
   docker run -p 5000:5000 mlops-project-9
   ```

### Kubernetes Deployment

1. Apply the manifests:
   ```bash
   kubectl apply -f manifests/
   ```

2. Check the deployment status:
   ```bash
   kubectl get pods
   kubectl get services
   ```

### Jupyter Notebook

1. Launch Jupyter:
   ```bash
   jupyter notebook
   ```

2. Open `notebook/notebook.ipynb` for exploratory data analysis.

## API Endpoints

- `GET /`: Home page with web interface.
- `POST /predict`: Endpoint for model predictions (expects JSON input).

## Configuration

- Modify `application.py` for Flask app settings.
- Update `Dockerfile` for container configuration.
- Adjust `Jenkinsfile` for CI/CD pipeline customization.
- Edit Kubernetes manifests in `manifests/` for deployment settings.

## Data

- Raw data should be placed in `artifacts/raw/`.
- Processed data is stored in `artifacts/processed/`.
- Models are saved in `artifacts/models/`.

## Logging

Logs are written to the `logs/` directory. Configure logging levels in `src/logger.py`.

## Contributing

1. Fork the repository.
2. Create a feature branch.
3. Make your changes.
4. Run tests and ensure code quality.
5. Submit a pull request.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Contact

For questions or support, please contact the project maintainer.