---
title: "Deploy Azure VM using Terraform & Terragrunt"
date: 2025-04-14
draft: false
description: "Learn how to deploy an Azure Virtual Machine using a modular Terraform setup and manage it with Terragrunt. Includes sample code and real-world structure."
keywords: ["Terraform", "Terragrunt", "Azure VM", "Infrastructure as Code", "IaC", "Terraform Modules", "Azure DevOps", "VNet", "Subnet", "Linux VM"]
---

## 🚀 Introduction

In this post, we’ll walk through a practical example of deploying an Azure **Virtual Machine** using a **reusable Terraform module**, and orchestrating the inputs with **Terragrunt**.

Whether you're spinning up a dev VM or preparing infrastructure for your next project, this setup is flexible, scalable, and clean — ideal for managing multiple environments with minimal duplication.

---

## 🔗 Code Repository

All source code is hosted publicly on GitHub:  
📁 **Terraform Module**: [`tf-brickstack/azure-vm-module`](https://github.com/vsaxena2711/tf-brickstack/tree/main/azure-vm-module)

📄 **Terragrunt Configuration**:  
Refer to this sample config to see how inputs are passed:  
👉 [`terragrunt.hcl`](https://github.com/vsaxena2711/tg-brickflow/blob/main/azure/dev/vm/terragrunt.hcl)

---

## 💡 Why This Setup?

This approach shows:
- ✅ **Modular Terraform**: Write once, reuse everywhere
- 🧠 **Clean Separation**: Code (Terraform) vs Config (Terragrunt)
- 🔄 **Environment Agility**: Easily switch between dev, stage, prod
- 🔐 **Better Secrets Management**: Use Terragrunt for secure input abstraction

---

## 📦 What the Module Includes

This Terraform module provisions the following Azure resources:

- **Resource Group**
- **Virtual Network** + Subnet
- **Network Interface**
- **Linux Virtual Machine** (Ubuntu)

---

## 🛠️ How Terragrunt Helps

Terragrunt is like a smart wrapper around Terraform.

You define your core infrastructure using Terraform — and use Terragrunt to:
- Pass input variables cleanly
- Reuse backend settings and provider configs
- Handle dependencies (e.g., shared subnets or identities)
- Manage multi-env deployments without duplicating `.tf` files

**Sample Terragrunt usage:**

```hcl
terraform {
  source = "git::https://github.com/vsaxena2711/tf-brickstack.git//azure-vm-module?ref=main"
}

inputs = {
  vm_name       = "vm-dev-001"
  location      = "East US"
  admin_user    = "azureuser"
  vm_size       = "Standard_B1s"
  rg_name       = "rg-dev-vm"
  vnet_name     = "vnet-dev"
  subnet_name   = "subnet-dev"
}
