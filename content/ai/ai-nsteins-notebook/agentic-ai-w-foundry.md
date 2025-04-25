---
title: "🧠 Create agentic AI solutions with Azure AI Foundry"
date: 2025-04-23
categories: ["AI-nstein's Notebook"]
tags: ["Azure AI Foundry", "AI Skills Fest", "Agentic AI", "Microsoft Learn"]
draft: true
---
> As part of the **Microsoft AI Skills Fest**, I participated in the challenge **"Create Agentic AI Solutions with Azure AI Foundry"** — and here are my key takeaways from Module 1 of the learning journey.

---
## 📌 Module 1: Plan and Prepare for AI Development on Azure

I’ve kicked off the **AI Skills Fest Challenge** by diving into Module 1: *Plan and prepare to develop AI solutions on Azure*. This module laid the foundation for building intelligent apps using the **Azure AI Foundry** platform and walked through key AI concepts, tools, and best practices.

### 🤖 What is AI Capable Of?

Modern applications can tap into a wide range of AI capabilities:

- **Generative AI** – Create fresh responses to prompts. Think auto-generated property listings for real estate apps.
- **Agents** – Intelligent assistants that can take actions, like helping schedule meetings or book rides.
- **Computer Vision** – Recognize objects in photos, generate captions, or identify items in a shopping basket.
- **Speech Services** – Convert text to speech and vice versa for natural conversation interfaces.
- **Natural Language Processing (NLP)** – Analyze and summarize text, detect sentiment, or categorize messages.
- **Information Extraction** – Pull structured data from receipts, images, or audio files.
- **Decision Support** – Predict outcomes using historical data (e.g., real estate trends from demographics).

### 🧰 Azure AI Services Highlights

A few powerhouse services that form the Azure AI toolkit:

- **Azure OpenAI** – Home of GPT models and DALL-E image generation.
- **AI Vision** – Object recognition, image tagging, text reading.
- **AI Speech** – Transcribe, synthesize, and translate speech.
- **AI Language** – Sentiment analysis, summarization, and Q&A systems.
- **AI Translator & Content Safety** – Translate content and ensure it’s appropriate.
- **AI Face & Custom Vision** – Face recognition and custom image models.
- **Document Intelligence & Content Understanding** – Extract and understand data from forms, docs, and media.
- **AI Search** – Combine AI skills and search to create powerful knowledge experiences.

### 🧩 Choosing Between Standalone or Unified Services

You can either:
- Use **individual services** (like Vision or Language) for flexibility and cost savings.
- Or go with a **multi-service AI resource** that bundles key services (OpenAI, Vision, Language, etc.) into one.

### 🏗️ What is Azure AI Foundry?

It’s a one-stop shop for AI development:
- **Visual Portal + SDK** for managing everything from models to data.
- Use **Hubs** to centralize shared resources.
- Create **Projects** within hubs for specific AI applications.

🧪 Projects come packed with:
- Prompt playgrounds
- Model catalog (including Hugging Face!)
- Fine-tuning tools
- Prompt Flow for orchestration
- Hosted dev environments (VS Code containers)
- Evaluation and security tools

### 📦 Plan Smart: Foundry Considerations

- **Structure:** Use hubs for teams/departments and projects for solutions.
- **Security:** Assign roles like Owner, Contributor, or Reader at both hub and project levels.
- **Region & Costs:** Services may vary by region. Track compute, storage, and quota limits.

### 🛠️ Developer Toolkit

- **VS Code Container** – Prebuilt with Azure SDKs, ready to code in the browser or locally.
- **GitHub + Copilot** – Seamless DevOps and code suggestions.
- **SDKs & APIs** – Python, Node, Java, C#, and more. Includes SDKs for AI services, Prompt Flow, and AI Agents.

---
## 🔍 Module 2: Choose and Deploy Models in Azure AI Foundry

In this module, I explored the **Model Catalog** in Azure AI Foundry, a central place to find and deploy pre-built models tailored to specific generative AI needs.

### 🧠 Model Types: LLMs vs SLMs

- **Large Language Models (LLMs)** like GPT-4, Mistral Large, and Llama3 70B are great for advanced reasoning and long-context understanding.
- **Small Language Models (SLMs)** like Phi3 and Mistral OSS are lightweight and fast — ideal for edge devices and quick responses.

### 🧭 Task-Oriented Models

Beyond just language, some models can handle **multi-modal** input (text + images). For example:
- **GPT-4o** and **Phi3-vision** can understand both visual and textual data.
- **Embedding Models** like Ada and Cohere are great for search, recommendations, and RAG (Retrieval Augmented Generation) scenarios.

### 🌍 Domain-Specific Models

Some models are built for specific regions or industries:
- **Core42 JAIS** – Arabic LLM
- **Mistral Large** – European language optimized
- **Nixtla TimeGEN-1** – Built for time-series forecasting (finance, supply chain)

### 🆚 Open vs Proprietary Models

- **Proprietary Models** (e.g., GPT-4, Command R+) offer enterprise-grade performance.
- **Open-Source Models** from Hugging Face, Meta, and others provide flexibility and customization at lower costs.

Regardless of the type, all models in the catalog follow enterprise-ready standards for **data privacy**, **security**, and **responsible AI**.

### 🚀 Can Your Solution Scale?

Once you’ve built a prototype, you need to plan for real-world workloads:
- **Where to deploy the model?**
- **How to monitor and optimize it?**
- **How to manage prompts and updates?**

Consider the full **GenAIOps lifecycle** for long-term success.

### 🎯 Prompt Engineering: Optimizing Model Responses

Crafting the right question is everything. Here's how to optimize prompts:

#### 🛠️ Prompt Patterns

- **Act as a Persona**: "You are a financial advisor..."
- **Suggest Better Questions**: Ask the model to refine your query.
- **Template-based Output**: Define a structure for the response.
- **Explain Reasoning**: Request rationale behind the answer.
- **Add Context**: Provide relevant background to narrow the focus.

### 🔧 Advanced Optimization Strategies

- **RAG** (Retrieval-Augmented Generation): Inject relevant data at runtime.
- **Fine-Tuning**: Customize a foundation model with example Q&A pairs.

---
## 🔍 Module 3: What is Azure AI Foundry SDK?

The **Azure AI Foundry SDK** is a powerful toolkit for developers to create applications using models and services defined within an Azure AI Foundry project. It supports Python and .NET, offering seamless integration to build generative AI applications.

### 📦 Install the SDK

To use the SDK in Python, install the core package:

```bash
pip install azure-ai-projects
```
### 🔗 Accessing Project Connections

Every **Azure AI Foundry project** includes connected resources—such as **Azure AI services**, **Storage**, and **AI Search**—which are accessible using the `AIProjectClient` class in Python.

You can use the following methods from the `connections` property:

- `connections.list()`  
  *Lists all resource connections.*

- `connections.get(name, include_credentials=True)`  
  *Retrieves a specific connection, optionally including credentials.*

- `connections.get_default(connection_type, include_credentials=True)`  
  *Fetches the default connection of a specific type (e.g., Azure AI Service).*

### 💬 Creating a Chat Client

A common use case is building **chat applications** using **generative AI models**. The Azure AI Foundry SDK supports multiple model hosting options:

- **Azure AI model inference** – A shared endpoint that hosts multiple models.
- **Azure OpenAI service** – A dedicated endpoint for OpenAI models hosted in Azure.
- **Serverless API** – Each model is exposed via a unique serverless endpoint.
- **Managed compute** – Models hosted on custom infrastructure with unique endpoints.


### 🧑‍💻 Build Apps Using Different Deployment Types

#### ✅ Azure AI Model Inference

Use the `ChatCompletionsClient` class from the SDK to chat with deployed models.  
A key advantage of this approach is **easy model switching**—just update the model deployment name in your code to test against different models.

#### ✅ Azure OpenAI Service

Use the method `AIProjectClient.get_azure_openai_client()` to connect to the **Azure OpenAI service** resource in your project.  
This returns an **OpenAI client**, which you can use to seamlessly interact with models deployed to the Azure OpenAI service.

---
## 📚 References

- [Plan and prepare to develop AI solutions on Azure](https://learn.microsoft.com/en-us/training/modules/prepare-azure-ai-development/?ref=collection&listId=60yka7t2o8od52&sharingId=6A9F03F25E12DA9E&wt.mc_id=aiskillsfest_msftlearn_training_wwl_challenge_tech)  
- [Choose and deploy models from the model catalog in Azure AI Foundry portal](https://learn.microsoft.com/en-us/training/modules/explore-models-azure-ai-studio/?ref=collection&listId=60yka7t2o8od52&sharingId=6A9F03F25E12DA9E&wt.mc_id=aiskillsfest_msftlearn_training_wwl_challenge_tech)
- [Develop an AI app with the Azure AI Foundry SDK](https://learn.microsoft.com/en-us/training/modules/ai-foundry-sdk/?wt.mc_id=challenges_active_registration_confirmation_email_learn)

