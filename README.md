##  Tools and Technologies Used
- **Terraform**: For provisioning infrastructure on Azure.
- **Ansible**: For automated server configuration.
- **Docker**: For containerizing the web application.
- **Git Actions**: For CI/CD pipeline setup.

##  Deployment Steps

### Prerequisites
- Azure account
- Terraform installed on your local machine
- Ansible installed on your local machine
- Git

Step 1: Terraform Setup
Navigate to the Terraform/ directory:
```bash
cd Terraform

Initialize Terraform:
```bash
terraform init

Review the plan:
```bash
terraform plan

Apply the configuration:
```bash
terraform apply

Step 2: Ansible Configuration
Navigate to the Ansible/ directory:
```bash
cd ../Ansible
Edit the inventory file:
Run with your Azure VM's public IP.

Run the playbook:
```bash
ansible-playbook -i inventory.ini playbook.yml

Step 3: Docker Deployment
Build the Docker image:
docker build -t my-web-app .
Run the container:
docker run -d -p 80:80 my-web-app
Verify the Nginx server is running by accessing the server IP

Step 4: Set up a GitHub Actions CI/CD pipeline to automate Docker container deployment.
Commit changes to the GitHub repository.
GitHub Actions workflow (.github/workflows/ci-cd-pipeline.yml) will:
Build and push the Docker image to Azure Container Registry (if configured).
Deploy the container on the Azure VM.
Monitor the pipeline execution in the GitHub Actions tab.


 Troubleshooting
Ensure that your Azure VM has the correct firewall rules to allow HTTP traffic (port 80).
If the Ansible playbook fails, verify the server IP and credentials in the inventory file.
