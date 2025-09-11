# 🚗 Vehicle ML Pipeline Project

### End-to-End Machine Learning Pipeline with **MongoDB, AWS, CI/CD, and Docker**  

This project demonstrates the design and deployment of a **production-ready ML system** built from scratch.  
It covers everything from **data ingestion** to **deployment on AWS EC2** using **Docker, GitHub Actions, and CI/CD pipelines**.  

Recruiters: This repository showcases my ability to not just build ML models, but also handle **MLOps, cloud integration, automation, and scalable deployment.**  

---

## 📌 Project Workflow  

1. **Project Setup**
   - Created project template using `template.py`.
   - Configured **local package imports** with `setup.py` and `pyproject.toml`.  
   - Virtual environment setup with Conda and requirements installation.  

   ```bash
   conda create -n vehicle python=3.10 -y
   conda activate vehicle
   pip install -r requirements.txt
   pip list   # Verify local packages
   ```

   **Core Project Modules:**
   ```
   ├── constant
   ├── config_entity
   ├── artifact_entity
   ├── component
   ├── pipeline
   ├── app.py / demo.py
   ```

---

2. **MongoDB Integration**
   - Setup **MongoDB Atlas cluster**, created DB user, and configured global access.  
   - Used **Python driver connection string** to push dataset from Jupyter Notebook (`mongoDB_demo.ipynb`) into MongoDB.  
   - Verified data upload via MongoDB Atlas Collections.  

---

3. **Data Ingestion**
   - Defined configurations in:
     - `constants.__init__.py`
     - `configuration.mongo_db_connections.py`
     - `data_access/proj1_data.py`  
   - Built `DataIngestionConfig` and `DataIngestionArtifact` classes.  
   - Implemented **data ingestion pipeline** inside `components.data_ingestion.py`.  
   - Connection URL stored securely via environment variables (`MONGODB_URL`).  

---

4. **Data Validation, Transformation & Model Training**
   - Added schema definition in `config/schema.yaml`.  
   - Developed components for:
     - ✅ Data Validation  
     - ✅ Data Transformation  
     - ✅ Model Training (with `estimator.py`).  

---

5. **AWS Integration**
   - Setup **IAM user**, **S3 bucket**, and configured credentials via env variables.  
   - Implemented `aws_connection.py` to interact with S3.  
   - Defined constants for model registry and evaluation thresholds.  
   - Built `s3_estimator.py` for pushing/pulling models to/from S3.  

---

6. **Model Evaluation & Model Pusher**
   - Added evaluation logic with threshold checks.  
   - Designed **Model Pusher** to move models to **AWS S3 model registry**.  

---

7. **Prediction Pipeline & Web App**
   - Developed `app.py` Flask application with templates & static files.  
   - Created **/predict** and **/training** endpoints.  

---

8. **CI/CD Pipeline with GitHub Actions**
   - Wrote **Dockerfile** and `.dockerignore`.  
   - Setup **GitHub Actions Workflow** (`aws.yaml`) for:
     - Building Docker image  
     - Pushing to **AWS ECR**  
     - Deploying on **AWS EC2** (self-hosted runner).  
   - Configured GitHub Secrets:
     ```
     AWS_ACCESS_KEY_ID
     AWS_SECRET_ACCESS_KEY
     AWS_DEFAULT_REGION
     ECR_REPO
     ```

---

9. **Deployment on AWS EC2**
   - Provisioned EC2 (Ubuntu 24.04, T2 Medium).  
   - Installed Docker and configured self-hosted GitHub runner.  
   - Opened inbound port `5080` for public access.  
   - Launched application via public IP + `:5080`.  

   **Final Workflow:**
   ```
   GitHub Commit ➝ GitHub Actions ➝ Build Docker Image ➝ Push to ECR ➝ Deploy on EC2
   ```

---

## ⚙️ Tech Stack  

- **Programming:** Python 3.10  
- **Data Storage:** MongoDB Atlas  
- **Cloud Services:** AWS S3, EC2, ECR, IAM  
- **MLOps:** Docker, GitHub Actions, CI/CD  
- **Frameworks:** Flask, Scikit-Learn, Pandas  
- **Environment:** Conda  

---

## 🚀 Key Highlights  

✔️ End-to-end ML pipeline from ingestion to deployment  
✔️ Cloud-native design with MongoDB + AWS S3 + EC2  
✔️ Automated CI/CD deployment with Docker & GitHub Actions  
✔️ Modular and production-ready project structure  
✔️ Real-time predictions via Flask API  

---

## 📂 Repository Structure  

```
├── src/
│   ├── constant/
│   ├── config_entity/
│   ├── artifact_entity/
│   ├── component/
│   ├── pipeline/
│   ├── aws_storage/
│   ├── entity/
│   ├── utils/
│   ├── app.py
│   └── demo.py
├── notebook/
│   ├── mongoDB_demo.ipynb
│   └── dataset/
├── requirements.txt
├── setup.py
├── pyproject.toml
├── Dockerfile
├── .dockerignore
├── .github/workflows/aws.yaml
└── README.md
```

---

## 📊 Results  

- Successfully ingested dataset into MongoDB.  
- Automated training pipeline with data validation, transformation, and training.  
- Model stored and versioned in AWS S3.  
- CI/CD pipeline ensures every commit is deployed to AWS EC2 with zero manual intervention.  

---

## 🏆 What This Project Shows Recruiters  

✅ Strong grasp of **Machine Learning pipelines**  
✅ Experience with **MongoDB, AWS (S3, EC2, IAM, ECR)**  
✅ **MLOps practices**: Docker, GitHub Actions, CI/CD  
✅ Ability to deliver **end-to-end production ML system**  
