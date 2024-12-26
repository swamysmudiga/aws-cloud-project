# WebApp Application

This repository contains the source code for the project 'webapp', a cloud-based backend web application developed for the course CSYE 6225: Network Structures and Cloud Computing, offered by Northeastern University and taken in Fall 2024.

## Languages and Technologies Used

The application is built using the following technologies, frameworks, and tools:
- **Java JDK**: Version 17
- **Spring Boot**: Version 3.3.3
- **PostgreSQL**: Version 16
- **Spring Data JPA** (Hibernate ORM)
- **Gradle**: Build tool
- **Postman**: To build and test APIs

## How to Run the Application

To run the application, follow these steps:

1. **Ensure prerequisites are installed**:
    - Java (JDK version 17)
    - PostgreSQL (version 16)

2. **Run the application**:
    - Navigate to the project directory in the command line.
    - Execute the following command to start the application:
      ```bash
      ./gradlew bootRun
      ```

3. **Build the application** (optional):
    - To build the application and generate a jar file, run the following command:
      ```bash
      ./gradlew clean build
      ```
    - This command will clean old artifacts, run test cases, and generate a jar file in the `/build/libs` directory.

4. **Run the jar file**:
    - If you wish to run the application from the generated jar file, execute the following command:
      ```bash
      java -jar <PATH_TO_JAR_FILE/JAR_FILE_NAME>
      ```
    - If your terminal is already in the correct directory, the `<PATH_TO_JAR_FILE>` can be omitted.

## API Endpoints

While running locally, you can access the application at `http://localhost:8080`. Below are the available endpoints:

### Health Check Endpoint

**GET**: `/healthz`
- Does **not** require authentication.
- Returns `200 OK` if the connection to the database is healthy.
- Returns `503 Service Unavailable` if the connection to the database is unsuccessful.
- Returns `400 Bad Request` if an invalid request parameter or request body is provided.

**POST**: `/healthz`
- Returns `405 Method Not Allowed`

**PUT**: `/healthz`
- Returns `405 Method Not Allowed`

**DELETE**: `/healthz`
- Returns `405 Method Not Allowed`

**PATCH**: `/healthz`
- Returns `405 Method Not Allowed`

## Additional Information

- This application uses **Spring Data JPA** for database interactions, with **PostgreSQL** serving as the backend database.
- API testing can be performed using **Postman** by hitting the listed endpoints.


# Terraform-AWS-Infrastructure as Code
Repository for course CSYE 6225 Network Structures and Cloud Computing offered by Northeastern University and taken in Fall 2024. This repository deals with using Terraform as infrastructure as Code platform and sets up Virtual Private Cloud (VPC) on AWS.

# How to run the application
- Install AWS cli and Terraform
- Run below command to set up AWS credentials on local device
  - aws configure --profile= YOUR_PROFILE_NAME
- Navigate to project repository on command line and run below Terraform commands
  - Initialize the repository: terraform init
  - Perform validation checks: terraform validate
  - Create execution plan: terraform plan
  - Apply changes mentioned in execution plan: terraform apply
  - Destroy existing vpc: terraform destroy

# Command to Import Demo Certificate
- Generic Command
  - aws acm import-certificate \
    --certificate file://path/to/certificate.pem \
    --private-key file://path/to/private_key.pem \
    --certificate-chain file://path/to/certificate_chain.pem \
    --region <region-name>

# Sample cmd to import demo certificate
- aws acm import-certificate --certificate fileb://certificate.pem  --private-key fileb://private_Key.pem --certificate-chain fileb://certificate_chain.pem --region us-east-1

# AWS Serverless Lambda Function

This Lambda function is designed to handle events triggered by an Amazon SNS topic. The primary purpose of this function is to process messages received from SNS, retrieve the username from the message, send a verification email to the user, and update an Amazon RDS database.

## Linked Repositories

Explore the two additional repositories that complement this project, containing code for the REST-based CRUD operations APIs (Webapp) developed in Java Enterprise Edition (J2EE) and the Infrastructure as Code (IaC) crafted in Terraform.

- [Webapp](https://github.com/swamysmudiga/webapp)
- [Infrastructure as Code](https://github.com/swamysmudiga/terraform-aws-infra)
- [AWS Lambda Serverless Function](https://github.com/swamysmudiga/aws-lambda-serverless)

## Functionality

This function performs the following tasks:

1. Retrieve the base64-decoded body from the SNS message
2. Decode the body and parse the JSON to retrieve the username
3. Send a verification email to the user using SMTP from Mailgun
4. Update database to reflect email sent

## Environment Variables

The following environment variables are configured for this Lambda function:

- **SMTP_HOST**: Host for the SMTP service (default: "smtp.mailgun.org").
- **SMTP_PORT**: Port number for the SMTP service (default: 587).
- **SMTP_USERNAME**: SMTP service username.
- **SMTP_PASSWORD**: SMTP service password.
- **SMTP_VERIFICATION_LINK**: URL for the verification link sent to users.
- **SMTP_FROM_EMAIL**: The email address from which the verification email is sent.
- **DB_HOST**: Endpoint of the Amazon RDS instance.
- **DB_USER**: Username for the Amazon RDS instance.
- **DB_PASSWORD**: Password for the Amazon RDS instance.
- **DB_DATABASE**: Name of the database on Amazon RDS.
- **DB_TABLE**: Name of the table in the database.
