---
title: "Download and Install Terraform and Azure CLI"
date: 2025-04-11
draft: false
---

## 🛠️ Download and Install Terraform & Azure CLI

Before diving into Infrastructure as Code, let’s set up the two most important tools you’ll need: **Terraform** and **Azure CLI**. These tools let you define, test, and manage your Azure resources directly from your machine.

---

## 1️⃣ Install Terraform

Terraform is distributed as a single binary. Here's how to install it on different platforms:

### 🔵 Windows

1. Visit the official download page:  
   👉 [https://developer.hashicorp.com/terraform/downloads](https://developer.hashicorp.com/terraform/downloads)

2. Download the **Windows (amd64)** zip file.

3. Extract it to a folder, e.g., `C:\Terraform`.

4. Add the folder to your **System PATH**:
   - Search for “Environment Variables”
   - Under *System variables*, find `Path` → Edit → New → Add `C:\Terraform`

5. Verify installation:
   ```powershell
   terraform -v
   ```

### 🍎 macOS (Using Homebrew)
```bash
brew tap hashicorp/tap
brew install hashicorp/tap/terraform
terraform -v
```

### 🐧 Linux
```bash
sudo apt-get update && sudo apt-get install -y gnupg software-properties-common curl
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install terraform
terraform -v
```

---

## 2️⃣ Install Azure CLI
Azure CLI helps you authenticate and manage Azure resources from your terminal.

### 🔵 Windows
1. Download from the official installer:
    👉 https://aka.ms/installazurecliwindows

2. Follow the installer steps.

3. Verify installation:
    ```bash
    az version
    ```
### 🍎 macOS
```bash
brew update && brew install azure-cli
az version
```


### 🐧 Linux (Debian/Ubuntu)
```bash
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
az version
```

---

## ✅ Next Step?
Once both tools are installed:

Login to Azure via CLI:
```bash
az login
```
You’re now ready to write your first Terraform script!

