Network Security Automation: Phishing Data Pipeline 
An end-to-end MLOps pipeline designed to automate the ingestion, validation, and transformation of network security data for phishing detection. This project features a professional modular architecture, containerization with Docker, and a production-ready API served via FastAPI.

System Architecture
The project is built using a component-based design, simulating industrial-scale machine learning workflows:

Data Ingestion: Automated migration of raw CSV data into a NoSQL MongoDB Atlas cluster.

Data Validation: Ensures data integrity via schema checking and automated drift detection.

Data Transformation: Features a modular preprocessing pipeline for engineering features ready for model training.

Model Training: Evaluation of classification models with integrated logging and artifact tracking.

Deployment: Fully containerized environment for consistent scaling across AWS EC2/ECR.

Tech Stack
Language: Python 3.10+

API Framework: FastAPI / Uvicorn

Database: MongoDB Atlas (NoSQL)

Infrastructure: Docker, AWS ECR, AWS EC2

Machine Learning: Scikit-learn, Pandas, NumPy

Logging: Custom Exception & Logging modules

Project Structure
Plaintext

network-security-automation/
├── networksecurity/           # Core Package
│   ├── components/            # Ingestion, Validation, & Transformation logic
│   ├── entity/                # Config & Artifact definitions
│   ├── pipeline/              # Training & Batch Prediction workflows
│   └── utils/                 # Utility functions for S3 and ML metrics
├── templates/                 # UI components for FastAPI frontend
├── Dockerfile                 # Containerization for cloud deployment
├── app.py                     # FastAPI entry point
├── push_data.py               # Data migration script (CSV to MongoDB)
└── setup.py                   # Package distribution configuration
 Getting Started
1. Clone the Repository
Bash

git clone https://github.com/SudhamshKalakonda/Network-Security-Automation.git
cd Network-Security-Automation
2. Environment Configuration
Create a .env file in the root directory to store your credentials:

Plaintext

MONGO_DB_URL="your_mongodb_connection_string"
AWS_ACCESS_KEY_ID="your_aws_key"
AWS_SECRET_ACCESS_KEY="your_aws_secret"
3. Installation
Bash

pip install -r requirements.txt
4. Execution
Ingest Data: python push_data.py

Start API: python app.py

Interactive Docs: View the Swagger UI at http://localhost:8080/docs

 Cloud Deployment (AWS)
This project is configured for CI/CD deployment using Docker:

Bash

# Build the image
docker build -t network-security-app .

# Run the container
docker run -p 8080:8080 network-security-app
