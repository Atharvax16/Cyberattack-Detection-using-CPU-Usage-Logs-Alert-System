# 🛡️ CyberAttacks Detection using CPU Usage Logs & Alert System

## 📘 Overview
It is a machine learning-based system designed to detect **CPU usage anomalies** that could indicate **fraudulent activity or cyberattacks**.  
It leverages **Amazon SageMaker** for model training and deployment, **AWS Lambda** for automation, and **Amazon SNS** for real-time alert notifications.

The goal is to provide an **AI-driven early warning system** that monitors CPU performance logs and identifies unusual patterns indicative of potential security incidents or resource abuse.

---

## 🚀 Features
- ✅ **Anomaly Detection:** Detects abnormal CPU usage patterns using an Isolation Forest model.  
- ☁️ **AWS SageMaker Integration:** Trains and deploys the model as an endpoint for real-time inference.  
- 🔔 **Automated Alerts:** Uses **AWS SNS** to send email or SMS alerts on detecting anomalies.  
- ⚙️ **Serverless Automation:** Employs **AWS Lambda** to trigger predictions and handle notifications.  
- 📈 **Scalable Architecture:** Easily extended for multiple system metrics or large-scale log ingestion.

---

## 🧠 Tech Stack
| Component | Technology |
|------------|-------------|
| **Model** | Isolation Forest (Scikit-learn) |
| **Data Preprocessing** | Pandas, NumPy, StandardScaler |
| **Cloud Services** | AWS SageMaker, Lambda, SNS |
| **Visualization** | Matplotlib |
| **Storage (optional)** | S3 for log data |
| **Language** | Python 3.x |

---

## 🧩 Workflow
1. **Data Collection:** Collect CPU usage logs with timestamps, business hour flags, and weekend indicators.  
2. **Feature Engineering:** Extract relevant features such as:
   - `cpu_usage`
   - `hour`
   - `is_business_hours`
   - `is_night`
   - `is_weekend`
3. **Model Training:** Train an Isolation Forest model to detect anomalies in CPU behavior.
4. **Model Deployment:** Deploy the trained model as a **SageMaker endpoint**.
5. **Lambda Trigger:** A Lambda function periodically sends new CPU logs to the endpoint for inference.
6. **SNS Notification:** If an anomaly is detected, an alert is sent to subscribed administrators or security teams.

---

## 📦 Installation & Setup

### Prerequisites
- AWS Account with access to SageMaker, Lambda, and SNS
- Python 3.8+
- IAM Role with necessary permissions
- Installed dependencies:
  ```bash
  pip install boto3 scikit-learn pandas numpy matplotlib joblib
