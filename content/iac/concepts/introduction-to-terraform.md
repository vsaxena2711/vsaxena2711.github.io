---
title: "Introduction to Terraform"
date: 2025-04-13
draft: false
---

## Introduction to Terraform

Terraform is an open-source Infrastructure as Code (IaC) tool developed by HashiCorp. It enables users to define and provision infrastructure resources across cloud providers using a declarative configuration language called HCL (HashiCorp Configuration Language).

---

## What is Terraform?

Think of Terraform like a blueprint for your infrastructure.

🏗️ **Real-world analogy**: Imagine you're building a house. You don't start by randomly placing bricks. Instead, you start with an architectural plan. That plan details how many rooms, where the doors and windows go, what the plumbing layout looks like, and so on. Similarly, Terraform lets you define the “plan” of your cloud infrastructure — virtual machines, networks, databases — all written in code.

Once this plan is in place, Terraform goes and builds the house — your infrastructure — exactly how it’s defined.

🔧 **Sample Terraform Code for Azure Resource Group:**

```hcl
provider "azurerm" {
  features {}
}

resource "azurerm_resource_group" "example" {
  name     = "rg-demo"
  location = "East US"
}
```
---

## Why Terraform?

- ✅ **Cloud Agnostic**: Works with major cloud providers like Azure, AWS, GCP, and others.
- 🧱 **Modular**: Write reusable modules for consistency and reduced duplication.
- 🔁 **Idempotent**: Re-applying the same configuration doesn’t create duplicate resources.
- 💡 **Dependency Management**: Terraform understands dependencies between resources and builds/destroys them in the correct order.
- 🔄 **Plan & Apply Workflow**: You can preview changes before applying them using `terraform plan`, and apply them safely with `terraform apply`.

---

## Core Concepts

### 1. Providers
Terraform interacts with different platforms via **providers** (e.g., AzureRM for Azure, AWS, Kubernetes, etc.).

### 2. Resources
**Resources** are the infrastructure components you want to manage — like `azurerm_virtual_machine`, `azurerm_storage_account`, etc.

### 3. State
Terraform maintains a **state file** that tracks the actual infrastructure it manages. This helps it detect drift and reconcile future changes.

### 4. Modules
**Modules** let you group resources and reuse them like functions — making your code cleaner and easier to manage.

---

## Common Terraform Workflow

```bash
# 1. Initialize the working directory
terraform init

# 2. Preview the changes
terraform plan

# 3. Apply the changes
terraform apply

```
## 💡 What’s Next?

Now that you’ve got the basics, we’ll explore real-world Terraform examples and how to structure your modules efficiently in Azure.