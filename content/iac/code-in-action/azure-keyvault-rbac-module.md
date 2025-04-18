---
title: "Create an Azure Key Vault (RBAC-based) using Terraform & Terragrunt"
date: 2025-04-18
draft: false
---

## 🔐 Overview

In this guide, we’ll build a verbose and reusable **Terraform module** for provisioning an **Azure Key Vault** using **RBAC-based access control** — the recommended model by Microsoft.

We'll also show how to call the module from a **Terragrunt** config file, keeping inputs clean and environment-friendly.

---

## 🤔 Access Policy vs. RBAC Model

Azure Key Vault supports two access models:

| Model        | Description                                                                 | Recommended? |
|--------------|-----------------------------------------------------------------------------|--------------|
| Access Policy| Classic model where you explicitly define what each principal can do       | ❌ Legacy     |
| RBAC         | Uses Azure’s Role-Based Access Control via Azure AD                         | ✅ Yes!       |

Microsoft recommends using **RBAC-based authorization** for improved security, flexibility, and centralized role management.


> ✅ **This post uses RBAC-based Key Vaults only. No `access_policy` blocks will be used in the module.**

---

## 🧱 Module Code Repository

Terraform module:
👉 [tf-brickstack:azure-kv-module](https://github.com/vsaxena2711/tf-brickstack/tree/main/azure-key-vault-module)

Terragrunt config:
👉 [tg-brickflow:azure-kv](https://github.com/vsaxena2711/tg-brickflow/tree/main/azure/dev/keyvault)

---

## ⚙️ What This Module Covers

The module provisions:

- A secure Azure Key Vault (RBAC-based)
- Network restrictions using `network_acls`
- Soft delete retention
- Tagging
- Public network access toggle
- Optional private access via subnet

---

## 📌 References
📘 [Terraform for Azure Key Vault](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/key_vault)

📘 [Best practices for using Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/general/best-practices)

📘 [Provide access to Key Vault objects with Azure RBAC](https://learn.microsoft.com/en-us/azure/key-vault/general/rbac-guide?tabs=azure-cli)
