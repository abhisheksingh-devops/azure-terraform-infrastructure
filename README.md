# Azure Infrastructure Automation using Terraform

## 📌 Project Overview

This project demonstrates automated provisioning of Microsoft Azure infrastructure using Terraform.

The infrastructure is managed using **Infrastructure as Code (IaC)** principles, making deployments repeatable, consistent, and version-controlled.

## 🛠️ Technologies Used

* Microsoft Azure
* Terraform
* Azure Resource Manager
* Git
* GitHub
* Azure Networking
* Infrastructure as Code (IaC)

## 🏗️ Azure Resources

The project provisions the following Azure resources:

* Resource Group
* Virtual Network (VNet)
* Subnets
* Network Security Groups (NSG)

## 📂 Project Structure

```text
azure-terraform-infrastructure/
│
├── main.tf
├── provider.tf
├── variables.tf
├── outputs.tf
├── terraform.tfvars.example
├── .gitignore
│
├── modules/
│   ├── resource_group/
│   └── vnet/
│
└── environments/
    └── dev/
```

## ⚙️ Terraform Workflow

### 1. Initialize Terraform

```bash
terraform init
```

### 2. Validate configuration

```bash
terraform validate
```

### 3. Create execution plan

```bash
terraform plan
```

### 4. Deploy infrastructure

```bash
terraform apply
```

### 5. Destroy infrastructure

```bash
terraform destroy
```

## 🔐 Security

Sensitive information is not stored in the repository.

Examples:

* Azure credentials
* Client secrets
* Subscription information
* Terraform state files
* Environment-specific secret values

Sensitive files are excluded using `.gitignore`.

## 🎯 Key Learning

Through this project, I practiced:

* Azure infrastructure provisioning
* Terraform configuration
* Terraform variables
* Reusable Terraform modules
* Infrastructure as Code
* Azure networking
* Git version control
* GitHub repository management

## 👨‍💻 Author

**Abhishek Singh**

DevOps Engineer | Azure | Terraform | CI/CD | Git | Linux

