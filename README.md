# Cloud-Training-Bootcamp

## Mission 1: Setting up Infrastructure on AWS and GCP

### AWS Setup:

Create a programmatic user named "terraform-en-1" with AmazonS3FullAccess.
Download access key as a CSV file.
Best practices for access key management.

### GCP Setup:

Download mission1.zip files.
Upload accessKeys.csv and mission1.zip to GCP Cloud Shell.
Prepare hands-on files.
Set AWS and GCP environment credentials.
Enable Container Registry API, Kubernetes Engine API, and Cloud SQL API.
Terraform Infrastructure Provisioning:

Modify tcb_aws_storage.tf in Google Editor.
Execute Terraform commands to provision infrastructure.

### Cloud SQL Configuration:

Configure Cloud SQL instance and connections.
Enable Service Networking API.
Add authorized networks.

## Mission 2: Application Deployment and Integration

### AWS Setup (Similar to Mission 1):

Create a programmatic user named "luxxy-covid-testing-system-en-app1" with AmazonS3FullAccess.
Download access key as a CSV file.

### GCP Setup (Continuation from Mission 1):

Create a new user on Cloud SQL.
Download mission2.zip files.
Connect to MySQL DB, create tables, and enable Cloud Build API.
Docker Image and Container Registry:

Build and push Docker image to Google Container Registry.

### Kubernetes Deployment:

Edit Kubernetes deployment file.
Connect to GKE and deploy the application.

### Testing:

Get the Public IP and test the application.

## Mission 3: Database Migration and Testing

### GCP Database Migration:

Download mission3.zip files.
Connect to Cloud SQL and import the SQL dump.

### AWS PDF Files Migration:

Connect to AWS Cloud Shell.
Download PDF files.
Sync PDF files with the S3 bucket.

### Testing:

Verify data import and file sync.
Test the application to view guest results.
This hands-on project involves setting up infrastructure on AWS and GCP, configuring databases, deploying an application, and performing data and file migrations between cloud platforms.

In a nutshell,

This bootcamp is divided into 3 missions:

1. Mission 1: To enable Multicloud architecture deployment through **Terraform**, with resources running in **AWS** and **Google Cloud Platform**.
2. Mission 2: To convert a database and an application to run on MultiCloud platform (**GCP** and **AWS**), including **Kubernetes** and **Docker** on this path.
3. Mission 3: To migrate the application files and data from a database, also known as **Cloud Migration** process.

