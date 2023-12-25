# Steps to implement Hands-on Project Mission 1

## Amazon Web Services

  1. Create an AWS account.
  2. Create IAM user and provide S3 full access.
  3. Download accesskeys.csv
                            
## Google Cloud Platform (GCP)

  1. Create an GCP account
  2. Upload **accessKeys.csv** and **mission1.zip** hands-on file to GCP Cloud Shell 
  3. Check if upload has been successfully completed using the command **ls -la**
  4. Hands-on files preparation

    ```
    mkdir mission1_en
    mkdir mission1_en
    mv mission1.zip mission1_en
    cd mission1_en
    unzip mission1.zip
    mv ~/accessKeys.csv mission1/en
    cd mission1/en
    chmod +x *.sh
    ```

  5. Run the following commands to prepare AWS and GCP environment. Authorize when asked.

    ```
    ./aws_set_credentials.sh accessKeys.csv
    gcloud config set project <project_id>
    ```

  6. Execute this command

       ```
       ./gcp_set_project.sh
       ```

  7. Enable the Container Registry API, Kubernetes Engine API and the Cloud SQL API

    ```
    gcloud services enable containerregistry.googleapis.com 
    gcloud services enable container.googleapis.com 
    gcloud services enable sqladmin.googleapis.com 
    ```

  > **IMPORTANT (DO NOT SKIP):**
  
  - **Before executing the Terraform commands, open the Google Editor and update the file tcb_aws_storage.tf replacing the bucket name with an unique name (AWS requires unique bucket names).**
      - Open the **tcb_aws_storage.tf** using Google Editor
      - On **line 4** of the file **tcb_aws_storage.tf**:
          - Replace **xxxx** with your name initials, using **5 letters** plus **5 random numbers**:
          Example: **luxxy-covid-testing-system-pdf-en-jerod29292**

  8. Run the following commands to finish provision infrastructure steps

    ```
    cd ~/mission1_en/mission1/en/terraform/
    terraform init
    terraform plan
    terraform apply
	  Type Yes and go ahead.
    ```

  > **Attention**:

  The Cloud SQL database may take **15 to 25 minutes** to create, always check the **CloudShell** and click **Reconnect** when the session expires (the session expires after **5 minutes** of inactivity by default)

  - The **warning** message at the end of **terraform apply** command execution is not a problem, please go ahead:

#### SQL Network Configuration

1. Once the Cloud SQL instance is provisioned, access the Cloud SQL service
2. Click on your Cloud SQL instance.
3. On the left side, under Primary Instance, click on **Connections**.
4. Go to **Networking** tab.
5. Under **Instance IP assignment**, select Private IP to enable.
    - Under **Associated networking**, select "Default"
    - Click **Set up Connection**
    - Click on **Enable API**, to enable Service Networking API (if asked).
    - Select **Use an automatically allocated IP range in your network**.
    - Click **Continue**
    - Click **Create Connection** and **wait a minutes until conclude.** You will see the message: “*Private services access connection for network default
     has been successfully created.”*
6. Under **Authorized Networks**, click "Add Network".
7. Under **New Network**, enter the following information:
    - **Name:** Public Access (For testing purposes only)
    - **Network**: 0.0.0.0/0
    - Click **Done**.
    - Click **Save** and ****wait to finish the update.
    This update may take from **10 to 20 minutes** to finish

