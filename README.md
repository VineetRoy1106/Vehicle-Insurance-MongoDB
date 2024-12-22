# 🚗 Vehicle Insurance Project

A comprehensive Machine Learning project pipeline to predict and analyze vehicle insurance data using MongoDB, AWS, and CI/CD integration. This project covers the entire ML lifecycle from data ingestion to deployment.

---

## 🌟 Features

- **Data Ingestion**: Fetch data from MongoDB and transform it into a structured DataFrame.
- **Data Validation**: Ensures data quality and schema compliance.
- **Data Transformation**: Preprocesses raw data for modeling.
- **Model Training**: Implements Machine Learning pipelines.
- **Model Evaluation**: Validates model performance.
- **Model Deployment**: Deploys the application using AWS and Docker.
- **CI/CD Integration**: Automated deployment using GitHub Actions and AWS EC2.

---

## 🚀 Getting Started

### Step 1: Setup Project Template
1. Execute the `template.py` script to create the project directory structure.
2. Update `setup.py` and `pyproject.toml` to configure local package imports. Refer to `crashcourse.txt` for details.

### Step 2: Virtual Environment
```bash
conda create -n vehicle python=3.10 -y
conda activate vehicle
pip install -r requirements.txt
pip list  # Verify local packages are installed
```

---

## 📂 MongoDB Setup

1. Sign up at [MongoDB Atlas](https://www.mongodb.com/atlas).
2. Create a project and a cluster with **M0 service**.
3. Add a user with a username and password.
4. Allow network access for IP `0.0.0.0/0`.
5. Copy the connection string from the "Connect" tab, replacing `<password>` with your database password.

---

## 🛠️ Project Components

### 1. **Data Handling**
- Push datasets to MongoDB using Jupyter notebooks (`mongoDB_demo.ipynb`).
- Fetch data as key-value pairs and transform them into a pandas DataFrame.

### 2. **Logging and Exception Handling**
- Implement logging (`src/logger.py`) and custom exception handling (`src/exception.py`) for robust debugging.

### 3. **Data Processing**
- **Data Validation**: Validate dataset schema using `config.schema.yaml`.
- **Data Transformation**: Use `src/components` to scale and encode data.
- **Model Training**: Implement machine learning models in `estimator.py`.

### 4. **AWS Setup**
- Create and configure IAM users with `AdministratorAccess`.
- Store trained models in an S3 bucket.
- Use EC2 instances for hosting and deploying Docker images.

### 5. **CI/CD Integration**
- Configure GitHub Actions with `.github/workflows/aws.yaml`.
- Use a self-hosted runner for seamless deployment.

---

## 🐳 Docker and Deployment

1. Create a Dockerfile and `.dockerignore` for containerization.
2. Push Docker images to AWS ECR:
   ```bash
   docker build -t vehicleproj .
   docker tag vehicleproj:latest <ECR_URI>:latest
   docker push <ECR_URI>:latest
   ```
3. Deploy the app on an EC2 instance and expose it on port 5080.

---

## 🌐 Access the Application

1. Open the EC2 instance's public IP address in your browser:
   ```
   http://<public_ip>:5080
   ```
2. Use `/training` endpoint to train models on the server.

---

## 📖 Workflow Overview

1. **Data Ingestion**: Fetch data from MongoDB.
2. **Data Validation**: Ensure data meets schema requirements.
3. **Data Transformation**: Preprocess data for ML models.
4. **Model Training**: Train and evaluate models.
5. **Model Deployment**: Deploy models using AWS and Docker.
6. **Continuous Integration**: Automate deployment with GitHub Actions.


