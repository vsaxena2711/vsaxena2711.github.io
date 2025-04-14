---
title: "Introduction to Terragrunt"
date: 2025-04-13
draft: false
---

## Introduction to Terragrunt

Terragrunt is a thin wrapper around Terraform that helps manage complex Infrastructure as Code (IaC) setups by providing powerful tools for automation, DRY (Don't Repeat Yourself) configuration, and environment-level orchestration.

If Terraform is your toolbox for provisioning infrastructure, then Terragrunt is the engineer who carries that toolbox from one environment to another, making sure all your tools are configured correctly and reused effectively.

---

## Real-World Analogy 🏗️🔁

🧰 **Terraform** is like a set of high-quality tools: a hammer, a drill, a tape measure, and so on. Each tool does a job, and you use them to build your cloud infrastructure.

👷 **Terragrunt** is like the project manager on a construction site. They don’t replace the tools — they help you **coordinate**, **reuse**, and **sequence** tasks across multiple rooms (environments, modules, regions).

- Imagine you’re building the same type of apartment in 3 cities. 
- Terraform helps you define how each apartment looks. 
- Terragrunt ensures you reuse the same design efficiently, but swap out the **location**, **size**, or **budget** without duplicating the blueprint.

---

## Why Terragrunt?

Terraform is powerful, but in larger setups it can become:

- ❌ Repetitive: Copy-pasting variables and backend configs.
- ❌ Hard to manage: Especially across environments like dev/staging/prod.
- ❌ Uncoordinated: When applying multiple modules that depend on each other.

Terragrunt helps solve these challenges with:

- ✅ **Keep your Terraform DRY**: Define shared configs once and reuse them.
- ✅ **Hierarchical Configuration**: Use `terragrunt.hcl` to inherit settings across folders.
- ✅ **Remote State Management**: Automatically configure backends per environment.
- ✅ **Module Orchestration**: Automatically apply dependencies between modules.
- ✅ **Multi-Environment Deployments**: Easily switch between environments by using separate `terragrunt.hcl` files with unique configurations.

---

## Key Features

### 1. Terragrunt HCL Wrapper
Terragrunt uses its own `terragrunt.hcl` files to wrap Terraform code and inject inputs dynamically.

```hcl
terraform {
  source = "../modules/vnet"
}

inputs = {
  vnet_name = "dev-vnet"
  location  = "eastus2"
}
```

### 2. Remote Backend Simplification
Define backend settings once and inherit across all child modules.
```hcl
remote_state {
  backend = "azurerm"
  config = {
    resource_group_name  = "rg-tfstate"
    storage_account_name = "sttfstate"
    container_name       = "tfstate"
    key                  = "${path_relative_to_include()}/terraform.tfstate"
  }
}
```
This avoids repetition of the same backend block in every Terraform module.

### 3. Dependency Handling
Terragrunt makes it easier to coordinate modules that depend on outputs from other modules.
```hcl
dependency "network" {
  config_path = "../network"
  mock_outputs = {
    subnet_id = "/subscriptions/xxxx/resourceGroups/dev-rg/providers/Microsoft.Network/virtualNetworks/dev-vnet/subnets/subnet1"
  }
}
```
This lets one module (e.g., app or database) pull outputs from another (e.g., networking) during provisioning.

---

## When to Use Terragrunt?
Terragrunt is ideal for:

📁 Large, multi-module Terraform projects

🔐 Environments with shared secrets and remote state

👥 Teams managing infrastructure at scale

🔄 Projects that need orchestration and reusability across environments

---

## Final Thoughts
Terraform is great when you're just starting out — small modules, a single environment. But as your cloud footprint grows, Terragrunt helps you scale safely and smartly by avoiding repetition and enforcing structure.

🧠 Think of Terragrunt as Terraform's config manager and automation engine — not a replacement, but a layer of wisdom on top.