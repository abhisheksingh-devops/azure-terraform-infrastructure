<div align="center">

# 🚀 Azure Infrastructure Automation using Terraform

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=23&duration=3000&pause=1000&color=0078D4&center=true&vCenter=true&width=750&lines=Azure+Infrastructure+Automation;Infrastructure+as+Code+%28IaC%29;Terraform+Modules+%7C+for_each;Automating+Cloud+Infrastructure" />

### ☁️ Microsoft Azure | Terraform | IaC | Cloud Automation

<br/>

<img src="https://img.shields.io/badge/Azure-Cloud-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white"/>
<img src="https://img.shields.io/badge/Terraform-IaC-7B42BC?style=for-the-badge&logo=terraform&logoColor=white"/>
<img src="https://img.shields.io/badge/Git-Version_Control-F05032?style=for-the-badge&logo=git&logoColor=white"/>
<img src="https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge&logo=github&logoColor=white"/>

<br/><br/>

<img src="https://skillicons.dev/icons?i=azure,terraform,git,github,linux,vscode&theme=dark" />

</div>

---

## 📌 Project Overview

This project demonstrates automated provisioning of **Microsoft Azure infrastructure using Terraform**.

The infrastructure is managed using **Infrastructure as Code (IaC)** principles, making deployments repeatable, consistent, and easy to maintain.

The project uses **reusable Terraform modules** and **`for_each`** to dynamically create multiple Azure resources without repeating resource blocks.

### 🎯 Project Objectives

* Automate Azure infrastructure provisioning.
* Implement Infrastructure as Code.
* Build reusable Terraform modules.
* Create multiple Azure resources dynamically.
* Manage infrastructure using Terraform variables.
* Maintain infrastructure code using Git and GitHub.

---

## 🛠️ Technologies Used

<div align="center">

| Technology                | Purpose                     |
| :------------------------ | :-------------------------- |
| ☁️ Microsoft Azure        | Cloud Infrastructure        |
| 🟣 Terraform              | Infrastructure as Code      |
| 🔷 Azure Resource Manager | Azure Resource Management   |
| 🌐 Azure Networking       | Virtual Network and Subnets |
| 🔀 Git                    | Version Control             |
| 🐙 GitHub                 | Source Code Management      |
| ⚙️ IaC                    | Infrastructure Automation   |

</div>

---

## 🏗️ Azure Resources

This project provisions the following Azure infrastructure:

| Azure Resource                | Description                   |
| :---------------------------- | :---------------------------- |
| Resource Group                | Organizes Azure resources     |
| Virtual Network (VNet)        | Provides private networking   |
| Multiple Subnets              | Divides network into segments |
| Network Security Groups (NSG) | Controls network traffic      |

### 🏛️ Infrastructure Architecture

```mermaid
flowchart TD
    A["👨‍💻 Developer"] --> B["GitHub Repository"]
    B --> C["Terraform Configuration"]
    C --> D["Resource Group"]
    D --> E["Virtual Network"]
    E --> F["Subnet 1"]
    E --> G["Subnet 2"]
    E --> H["Subnet 3"]
    F --> I["Network Security Group"]
    G --> J["Network Security Group"]
    H --> K["Network Security Group"]

    style A fill:#24292e,color:#fff
    style B fill:#24292e,color:#fff
    style C fill:#7B42BC,color:#fff
    style D fill:#0078D4,color:#fff
    style E fill:#0078D4,color:#fff
```

---

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

---

## 🔁 Terraform `for_each`

This project uses Terraform's **`for_each` meta-argument** to create multiple resources dynamically.

### Example: Subnet Creation

```hcl
variable "subnets" {
  type = any
}

resource "azurerm_subnet" "subnet" {
  for_each = var.subnets

  name                 = each.key
  address_prefixes     = [each.value]
  resource_group_name  = var.resource_group_name
  virtual_network_name = var.virtual_network_name
}
```

### ✨ Benefits of `for_each`

* ♻️ Reduces code duplication.
* ⚡ Creates multiple resources dynamically.
* 🔧 Makes Terraform configuration reusable.
* 📦 Makes infrastructure easier to maintain.
* 🗂️ Allows resources to be managed using maps.

---

## 🧩 Terraform Modules

This project uses reusable Terraform modules to organize infrastructure.

### 1. Resource Group Module

📁 `modules/resource_group/`

Responsible for creating and managing Azure Resource Groups.

### 2. VNet Module

📁 `modules/vnet/`

Responsible for creating Azure Virtual Networks and related networking resources.

---

## 🌍 Development Environment

📁 `environments/dev/`

The development environment contains:

| File               | Description                  |
| :----------------- | :--------------------------- |
| `main.tf`          | Module configuration         |
| `provider.tf`      | Azure provider configuration |
| `variables.tf`     | Input variable definitions   |
| `terraform.tfvars` | Environment-specific values  |

---

## ⚙️ Terraform Workflow

<div align="center">

```mermaid
flowchart TD
    A["🚀 Start"] --> B["terraform init"]
    B --> C["terraform validate"]
    C --> D["terraform plan"]
    D --> E["terraform apply"]
    E --> F["☁️ Azure Infrastructure"]
    F --> G["terraform destroy"]

    style A fill:#24292e,color:#fff
    style B fill:#7B42BC,color:#fff
    style C fill:#7B42BC,color:#fff
    style D fill:#0078D4,color:#fff
    style E fill:#0078D4,color:#fff
    style F fill:#00875A,color:#fff
    style G fill:#C0392B,color:#fff
```

</div>

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

---

## 🔐 Security Best Practices

* Never commit passwords or credentials to GitHub.
* Exclude Terraform state files from version control.
* Exclude the `.terraform/` directory.
* Use secure Azure authentication methods.
* Manage sensitive information securely.
* Follow the principle of least privilege.

---

## 🎯 Key Learning Outcomes

Through this project, I practiced:

* ☁️ Azure Infrastructure Provisioning
* 🏗️ Terraform Configuration
* 📦 Terraform Variables
* 🧩 Reusable Terraform Modules
* 🔁 Terraform `for_each`
* ⚡ Dynamic Resource Creation
* 🌐 Azure Networking
* 🔐 Infrastructure as Code (IaC)
* 🔀 Git Version Control
* 🐙 GitHub Repository Management

**🚀 Project Status**
<p align="center">
  <img src="https://img.shields.io/badge/Project%20Status-In%20Progress-orange?style=for-the-badge&logo=github&logoColor=white&labelColor=181717"/>
</p>
---

## 👨‍💻 Author

<div align="center">

# Abhishek Singh

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=18&pause=1000&color=0078D4&center=true&vCenter=true&width=600&lines=DevOps+Engineer;Azure+%7C+Terraform+%7C+CI%2FCD;Cloud+Infrastructure+Automation" />

[![GitHub](https://img.shields.io/badge/GitHub-abhisheksingh--devops-181717?style=for-the-badge\&logo=github)](https://github.com/abhisheksingh-devops)

### Building 🚀 Automating ⚙️ Learning 📚

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0078D4,100:7B42BC&height=120&section=footer" width="100%"/>

</div>
