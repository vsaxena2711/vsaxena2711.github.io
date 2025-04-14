---
title: "Install Terragrunt"
date: 2025-04-13
draft: false
---

## 🛠️ How to Install Terragrunt

Terragrunt is a thin wrapper around Terraform that provides extra tools for managing configurations, remote backends, dependencies, and DRY (Don't Repeat Yourself) practices.

Let’s walk through the steps to install it.

---

## 🧑‍💻 Step-by-Step: Installing Terragrunt

### ✅ Prerequisites

Make sure **Terraform** is already installed on your system.  
If not, check out: [🧱 Install Terraform & Azure CLI](/iac/concepts/download-and-install-terraform-azurecli)

---

### 🪟 For Windows

1. **Download the latest Terragrunt `.exe`:**  
   Visit the [Terragrunt releases page](https://github.com/gruntwork-io/terragrunt/releases).

2. Find the latest version and download `terragrunt_windows_amd64.exe`.

3. **Rename and move it to a directory in your PATH:**
   ```powershell
   Rename-Item .\terragrunt_windows_amd64.exe terragrunt.exe
   Move-Item .\terragrunt.exe "C:\Program Files\Terragrunt\terragrunt.exe"
    ```
4. Add the folder (e.g., `C:\Program Files\Terragrunt`) to your Environment Variables → `Path`.

5. Restart your terminal and test:
   ```powershell
    terragrunt --version
    ```

---

### 🍎 For macOS
1. Using **Homebrew**:
    ```bash
    brew install terragrunt
    ```
2. Verify the installation:
    ```bash
    terragrunt --version
    ```

---

### 🐧 For Linux
1. Download the latest binary:
    ```bash
    curl -L -o terragrunt https://github.com/gruntwork-io/terragrunt/releases/latest/download/terragrunt_linux_amd64
    ```
2. Move it to your bin folder and make it executable:
    ```bash
    chmod +x terragrunt
    sudo mv terragrunt /usr/local/bin/
    ```
3. Verify:
    ```bash
    terragrunt --version
    ```

---

## 📁 Directory Structure (Optional Best Practice)

Once installed, you can start structuring your project like this:
```bash
project-root/
  └── terragrunt.hcl
  └── env/
      └── dev/
          └── terragrunt.hcl
      └── prod/
          └── terragrunt.hcl
```

---

## 🎯 Final Notes
- Terragrunt is often used in CI/CD pipelines and large enterprise setups.

- You only need to install it once per machine.

- Always match your Terragrunt version to the Terraform version it supports.
