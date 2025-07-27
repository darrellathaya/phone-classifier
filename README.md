# Phone Price Predictor

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Railway](https://img.shields.io/badge/Railway-000000?style=for-the-badge&logo=railway&logoColor=white)
![SonarQube](https://img.shields.io/badge/SonarQube-4E9BCD?style=for-the-badge&logo=sonarqube&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)


## Project Description

**Phone Price Predictor** is a machine learning pipeline project that classifies mobile phones into different price categories and predicts exact price estimates based on hardware specifications. This project implements an **end-to-end MLOps workflow** using version-controlled data, GitHub Actions for automation, and FastAPI for deployment.

The system demonstrates how **automated training**, **versioned model storage**, and **CI/CD integration** can work together to keep a machine learning application reliable, testable, and production-ready.

It includes a fully working web app that allows users to input phone specs and receive both a classification label and a regression-based price prediction.

  
## Features

- Model training and evaluation with **scikit-learn**  
- Live model serving with **FastAPI**  
- CI/CD via **GitHub Actions** triggered on data changes  
- Regression and classification support  
- Model versioning and metrics tracking  
- Docker-compatible and ready for deployment  


## Technologies Used

- **Python** — Core language for ML pipeline  
- **scikit-learn** — Machine learning models  
- **FastAPI** — REST API interface for predictions  
- **GitHub Actions** — CI/CD automation for model training  
- **Docker** — Optional containerized deployment  


## Getting Started

### Prerequisites

- Python 3.8+  
- Git  
- (Optional) Docker  
- (Optional) Azure CLI (for deployment)

### Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/darrellathaya/phone-predictor.git
   cd phone-predictor
   ```

2. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **(Optional) Install Azure CLI**

   **Windows**
   ```powershell
   Invoke-WebRequest -Uri https://aka.ms/installazurecliwindows -OutFile .\AzureCLI.msi
   Start-Process .\AzureCLI.msi
   ```

   **Linux**
   ```bash
   curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
   ```


## Usage Guide

### Train the Model Manually
```bash
python src/model.py
```

### Start the Web App
```bash
uvicorn app.main:app --reload
```

Then visit `http://localhost:8000` in your browser.

### Trigger CI/CD on GitHub
- Update `data/raw/train.csv` and push to the repository.
- GitHub Actions will automatically:
  - Retrain models
  - Evaluate performance
  - Save results to the `models/` directory


## Project Structure

```
phone-predictor/
├── .github/
│   └── workflows/                  # CI/CD pipelines
│       ├── ci.yml
│       ├── cd.yml
│       └── azure-static-web-apps.yml
│
├── app/                            # FastAPI app
│   ├── main.py
│   └── templates/
│       └── index.html
│
├── data/
│   └── raw/
│       └── train.csv              # Training dataset
│
├── models/                         # Saved models and performance logs
│   ├── price_range_model.pkl
│   ├── price_regression_model.pkl
│   ├── chipset_encoder.pkl
│   ├── meta.json
│   ├── accuracy.txt
│   └── regression_metrics.txt
│
├── src/
│   ├── train.py                   # Modular training logic
│   └── model.py                   # Main training script
│
├── requirements.txt
├── Dockerfile
└── README.md
```

---

## License

This project is licensed under the MIT License.
