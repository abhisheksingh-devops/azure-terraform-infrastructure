# Azure Infrastructure Automation using Terraform

## 📌 Project Overview

This project demonstrates automated provisioning of **Microsoft Azure infrastructure using Terraform**.

The infrastructure is managed using **Infrastructure as Code (IaC)** principles, making deployments repeatable, consistent, and easy to maintain.

The project uses **reusable Terraform modules** and **`for_each`** to dynamically create multiple Azure resources.

## 🛠️ Technologies Used

* Microsoft Azure
* Terraform
* Azure Resource Manager
* Azure Networking
* Git
* GitHub
* Infrastructure as Code (IaC)

## 🏗️ Azure Resources

This project provisions Azure infrastructure including:

* Resource Group
* Virtual Network (VNet)
* Multiple Subnets
* Network Security Groups (NSG)

Terraform **`for_each`** is used to create multiple resources dynamically without repeating Terraform resource blocks.

## 📂 Project Structure

```text
azure-terraform-infrastructure/
│
├── README.md
├── .gitignore
│
├── modules/
│   ├── resource_group/
│   │   ├── main.tf
│   │   └── variables.tf
│   │
│   └── vnet/
│       ├── main.tf
│       └── variables.tf
│
└── environments/
    └── dev/
        ├── main.tf
        ├── provider.tf
        ├── variables.tf
        └── terraform.tfvars
```

## 🔁 Terraform `for_each`

This project uses Terraform **`for_each`** for dynamic resource creation.

For example, multiple subnets can be created from a map:

```hcl
variable "subnets" {
  type = map(string)
}
```

The `for_each` meta-argument can then be used to create each subnet dynamically:

```hcl
resource "azurerm_subnet" "subnet" {
  for_each = var.subnets

  name                 = each.key
  address_prefixes     = [each.value]
  resource_group_name  = var.resource_group_name
  virtual_network_name = var.virtual_network_name
}
```

### Benefits of `for_each`

* Reduces code duplication
* Creates multiple resources dynamically
* Makes Terraform configuration reusable
* Makes infrastructure easier to maintain
* Allows resources to be managed using maps

## 🧩 Terraform Modules

The project uses reusable Terraform modules:

### Resource Group Module

Located at:

```text
modules/resource_group/
```

This module is responsible for creating the Azure Resource Group.

### VNet Module

Located at:

```text
modules/vnet/
```

This module is responsible for creating the Azure Virtual Network and related networking resources.

## 🌍 Development Environment

The development environment is located at:

```text
environments/dev/
```

It contains:

* `main.tf` — module configuration
* `provider.tf` — Azure provider configuration
* `variables.tf` — input variable definitions
* `terraform.tfvars` — environment-specific values

## ⚙️ Terraform Workflow

### 1. Initialize Terraform

```bash
terraform init
```

### 2. Validate Configuration

```bash
terraform validate
```

### 3. Create Execution Plan

```bash
terraform plan
```

### 4. Deploy Infrastructure

```bash
terraform apply
```

### 5. Destroy Infrastructure

```bash
terraform destroy
```

## 🔐 Security

Sensitive information should not be committed to GitHub.

The `.gitignore` file is used to exclude files such as:

* Terraform state files
* `.terraform/` directory
* Environment-specific sensitive files
* Secret files
* Local Terraform files

Azure credentials and secrets should be managed securely using appropriate authentication methods instead of storing them directly in the repository.

## 🎯 Key Learning

Through this project, I practiced:

* Azure infrastructure provisioning
* Terraform configuration
* Terraform variables
* Reusable Terraform modules
* Terraform `for_each`
* Dynamic resource creation
* Azure networking
* Infrastructure as Code (IaC)
* Git version control
* GitHub repository management



## 👨‍💻 Author

**Abhishek Singh**

DevOps Engineer | Azure | Terraform | CI/CD | Git | Linux
