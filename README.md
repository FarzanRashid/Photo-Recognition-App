# Photo Recognition Application

This project is a **Flask web application** that demonstrates seamless integration with multiple **Amazon Web Services (AWS)** including **EC2**, **RDS**, **S3**, **Rekognition**, and **Cognito**.  


Through this app, users can securely **sign in**, **upload photos**, and get **AI-powered image recognition results** — such as detecting objects, scenes, and faces — all powered by AWS.

---

## Key Features

-  **Secure User Authentication with Amazon Cognito**  
  Users can sign up and log in through AWS Cognito’s hosted UI. Flask handles the OAuth2 callback and session creation.

-  **Photo Recognition using Amazon Rekognition**  
  Upload an image and the app uses AWS Rekognition to analyze it.  
  It returns:
  - Detected labels (e.g., “Person”, “Car”, “Dog”)  
  - Confidence scores  
  - Face detection

- **Flask Integration with AWS SDK (boto3)**  
  Demonstrates how to connect a Flask backend with AWS APIs using the `boto3` SDK.

- **Secure Token Handling**  
  Cognito tokens (ID and Access tokens) are validated and used securely within the app.

- ⚙️ **Environment-based Configuration**  
  All AWS credentials and configuration values are managed securely (no hardcoding).

- *Local HTTPS Support**  
  Includes setup for self-signed certificates for secure local testing.

---

## Prerequisites

Before running the app, ensure you have:
- Python 3.8+
- An **AWS account**
- A configured **Cognito User Pool** and **App Client**
- (Optional) An **S3 bucket** for storing uploaded photos
- An IAM role or user with permissions:
  - `AmazonRekognitionFullAccess`
  - `AmazonCognitoReadOnly`
  - `AmazonS3FullAccess` (if using S3)

---

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/FarzanRashid/Photo-Recognition-App.gitnition
   
2. **Create a virtual environment**
    ```bash
   python3 -m venv venv
   source venv/bin/activate


3. **Install dependencies**
    ```bash
    pip install -r requirements.txt


4. **Set environment variables**
    ```bash
    export AWS_REGION=us-west-2
    export COGNITO_CLIENT_ID=your_client_id
    export COGNITO_USER_POOL_ID=your_user_pool_id
    export COGNITO_DOMAIN=https://yourdomain.auth.us-west-2.amazoncognito.com
    export FLASK_ENV=development


## Running the App

1. **To start the Flask server**:
    ```bash
    python app.py


2. **Visit**:
   ```bash
   http://localhost:8080


3. **If using HTTPS (with local certs)**:
    ```bash
    python app.py --ssl

## Technologies Used

| Component          | Service / Library |
|--------------------|-------------------|
| **Backend**        | Flask (Python)    |
| **Authentication** | Amazon Cognito    |
| **AI / ML**        | Amazon Rekognition |
| **AWS SDK**        | boto3             |
| **File Storage**   | Amazon S3         |
| **Database**       | Amazon RDS        |
| **Frontend**       | HTML, CSS  |
