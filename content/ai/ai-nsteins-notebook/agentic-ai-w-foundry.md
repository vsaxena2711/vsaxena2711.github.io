---
title: "🧠 Create agentic AI solutions with Azure AI Foundry"
date: 2025-06-23
categories: ["AI-nstein's Notebook"]
tags: ["Azure AI Foundry", "AI Skills Fest", "Agentic AI", "Microsoft Learn"]
draft: false
---
> As part of the **Microsoft AI Skills Fest**, I participated in the challenge **"Create Agentic AI Solutions with Azure AI Foundry"** — and here are my key takeaways from Module 1 of the learning journey.

---
## 🔗 Quick Navigation

- [📌 Module 1: Plan and Prepare for AI Development on Azure](#-module-1-plan-and-prepare-for-ai-development-on-azure)
- [🔍 Module 2: Choose and Deploy Models in Azure AI Foundry](#-module-2-choose-and-deploy-models-in-azure-ai-foundry)
- [🔍 Module 3: What is Azure AI Foundry SDK?](#-module-3-what-is-azure-ai-foundry-sdk)
- [🤖 Module 4 : Get Started with AI Agent Development on Azure](#-module-4--get-started-with-ai-agent-development-on-azure)
- [📚 Module 5 : Develop a RAG-Based Solution with Your Own Data Using Azure AI Foundry](#-module-5--develop-a-rag-based-solution-with-your-own-data-using-azure-ai-foundry)
- [🔒 Module 6: Introduction to AI Agent Service Security Controls](#-module-6-introduction-to-ai-agent-service-security-controls)
- [🤖 Module 7 Recap: Develop an AI Agent with Azure AI Agent Service](#-module-7-recap-develop-an-ai-agent-with-azure-ai-agent-service)
- [🧩 Module 8 Recap: Integrate Custom Tools into Your AI Agent](#-module-8-recap-integrate-custom-tools-into-your-ai-agent)
- [🧠 Module 9 Recap: Orchestrate a Multi-Agent Solution Using Semantic Kernel](#-module-9-recap-orchestrate-a-multi-agent-solution-using-semantic-kernel)

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


## 🤔 What are AI Agents?

**AI agents** are intelligent software services that combine **generative AI models**, **contextual data**, and **automation capabilities** to perform tasks based on user input and environmental factors.

Example:  
An AI agent could help employees manage expense claims by answering questions about corporate policy and automatically submitting recurring claims like monthly cellphone bills, or routing claims to appropriate approvers.


## 🛠️ Options for Building AI Agents

Developers have several frameworks and SDKs available for creating AI agents:

- **Azure AI Agent Service**  
  Managed service based on OpenAI Assistants API, offering model choice, enterprise security, and deep integration with Azure AI Foundry.

- **OpenAI Assistants API**  
  Limited to OpenAI models, offering a smaller feature set compared to Azure AI Agent Service.

- **Semantic Kernel**  
  Open-source toolkit for building AI agents and orchestrating multi-agent workflows. Includes the Semantic Kernel Agent Framework for agent-specific solutions.

- **AutoGen**  
  Lightweight open-source framework ideal for rapid prototyping and research on agent development.

- **Microsoft 365 Agents SDK**  
  SDK to create agents that can be deployed across channels like Slack and Messenger, not limited to Microsoft 365 apps.

- **Microsoft Copilot Studio**  
  A low-code platform enabling "citizen developers" to quickly design and deploy agents using a visual interface integrated with Microsoft 365 or other channels.

---
## 🤖 Module 4 : Get Started with AI Agent Development on Azure
### 🚀 Azure AI Agent Service Overview

The **Azure AI Agent Service** (part of Azure AI Foundry) helps you **create, test, and manage AI agents** through:

- A **visual experience** in the Azure AI Foundry portal.
- A **code-first experience** using the Azure AI Foundry SDK.

#### 🧩 Components of an Azure AI Agent

- **Model**  
  A deployed generative AI model (e.g., OpenAI models or those from the Azure AI Foundry catalog) that powers the agent's reasoning and response generation.

- **Knowledge**  
  Contextual data sources that ground agent responses, including:
  - Bing search results
  - Azure AI Search indexes
  - Your custom documents and datasets

- **Tools**  
  Programmatic capabilities for task automation, such as:
  - Built-in search tools (Bing, Azure AI Search)
  - A code interpreter for Python execution
  - Custom tools built using your code or Azure Functions

---
## 📚 Module 5 : Develop a RAG-Based Solution with Your Own Data Using Azure AI Foundry

### 🚫 Ungrounded Prompts and Responses

Language models generate answers based solely on their training data, which is often vast but **uncontextualized**.  
This can lead to responses that sound logical but are inaccurate or even fictional.  
Example: Asking "Which product should I use for X?" could result in details about a non-existent product.

### 📌 Grounded Prompts and Responses

By **grounding** prompts with **relevant, factual data**, you can guide the model to produce **accurate and contextualized** answers.  
For example, grounding with a product catalog ensures the model recommends actual, available products.

### 🧠 How to Ground Your Language Model

Language models are great at generating natural text, but they often lack **specific domain knowledge**.  
To improve accuracy, you can apply **Retrieval Augmented Generation (RAG)**, which involves:

- Retrieving relevant data based on the user's prompt.
- Augmenting the prompt with retrieved data.
- Using a language model to generate the final response.

#### 🗂️ Adding Grounding Data in Azure AI Foundry

Azure AI Foundry allows you to upload your own data for grounding, connecting to:

- **Azure Blob Storage**
- **Azure Data Lake Storage Gen2**
- **Microsoft OneLake**

You can also upload files or folders directly into your AI Foundry project storage.

### 🔍 Make Your Data Searchable

For an agent to generate accurate answers, efficient searchability of your data is crucial.  
Azure AI Foundry integrates with **Azure AI Search** for powerful retrieval capabilities.

#### 🧮 Vector Indexing

Instead of relying only on text-based search, you can use a **vector index**—embedding your data into floating-point vectors to capture semantic meaning.

Example:  
Texts like *"The children played joyfully in the park."* and *"Kids happily ran around the playground."* have different words but similar meaning—captured through vector embeddings.

#### 🗃️ Creating a Search Index

A **search index** organizes your content, similar to a library catalog.  
It helps the search engine find relevant content quickly and efficiently.

#### 🔎 Searching the Index

You can query your index using:

- **Keyword search** – Based on exact terms.
- **Semantic search** – Based on meaning.
- **Vector search** – Based on semantic similarity using embeddings.
- **Hybrid search** – Combines multiple techniques for optimal results.

### 🔄 Implement RAG in a Prompt Flow

Once you upload your data and create an index, you can use **Prompt Flow** in Azure AI Foundry to orchestrate a **Retrieval Augmented Generation (RAG)** solution.

#### ⚙️ Key Steps for RAG Implementation

- Use a **sample** to create a chat flow.
- **Modify** the query based on chat history.
- **Look up** relevant information from your index.
- **Generate** prompt context.
- **Define** prompt variants for better interaction.
- **Chat** with grounded context in responses.

---
## 🔒 Module 6: Introduction to AI Agent Service Security Controls

### 🧠 Understanding the Azure AI Agent Service

The **Azure AI Agent Service** acts as a "smart" microservice to:

- Answer questions (via Retrieval Augmented Generation - RAG),
- Perform actions,
- Automate workflows.

It combines generative AI with tools that interact with real-world data.  
Since the service is **fully managed by Microsoft**, you don't need to worry about scaling, security, or infrastructure management.

However, it's important to still follow basic security principles:

- **Restrict access** using Azure RBAC (Role-Based Access Control).
- **Limit the agent's visibility** into sensitive data sources.
- **Control network access** both to and from the AI Agent service.

### 🛡️ Securing the Azure AI Agent Service

In Azure AI Foundry:

- **Projects** belong to **hubs**, which act as central governance points.
- Hubs manage **security**, **networking**, and **computing resources** across multiple projects.
- Admins can apply security controls through both the Azure AI Foundry portal and the Azure portal.

Key security features at the hub level include:

- **Role-Based Access Control** (RBAC)
- **Network Access Settings**
- **Monitoring Alerts, Metrics, and Logs**

Hubs and projects are stored inside a **resource group** in your Azure subscription, but Foundry abstracts much of the complexity for developers.

### 🔐 Azure AI Agent Service Role-Based Access Control (RBAC)

**Azure RBAC** controls who can create, manage, or use resources.

- Users from Microsoft Entra ID are assigned specific roles.
- **System-assigned managed identities** are used by hubs and inherited by projects.
- These identities handle secure data access and function execution on behalf of the agent.

You can add users and assign roles directly from the Azure AI Foundry portal:

- Navigate to the **Management Center** → **Users** (under hub or project).
- Select **New user** to add and assign a role.

### 🌐 Agent Service and Network Access

Network access for AI Agents is configured at the **hub level**—but only through the **Azure portal** (not the Foundry portal).

If your resources are outside Azure (e.g., in an on-premises network or a different VNet), you need:

1. **Application Gateway**: Acts as a bridge between Azure and your non-Azure resources.
2. **Private Endpoint**: Created from the Azure AI Foundry hub’s managed VNet to the Application Gateway for **private, secure access**—keeping traffic off the public internet.
---
## 🤖 Module 7 Recap: Develop an AI Agent with Azure AI Agent Service
### 🧠 What is an AI Agent?

An **AI agent** is an intelligent software service that uses **generative AI** to understand context, make decisions, and take actions—independently executing workflows or tasks. Unlike traditional apps, AI agents operate autonomously and adapt to dynamic scenarios using grounding data and tools.

#### 💡 Why are AI Agents Useful?

- **Automate Routine Tasks** – Free up human time by automating repetitive tasks.
- **Enhance Decision-Making** – Process real-time data, analyze trends, and offer actionable insights.
- **Scalability** – Handle growing workloads without a proportional increase in manpower.
- **24/7 Availability** – Operate continuously, providing round-the-clock support or execution.

#### 📌 Example Use Cases

AI agents can be deployed in many roles:

- Personal productivity agents  
- Research assistants  
- Sales and marketing support  
- Customer service bots  
- Developer assistants

### ⚙️ How to Use Azure AI Agent Service

The **Azure AI Agent Service** enables developers to build AI agents that use large language models to automate tasks, make decisions, and respond to real-world inputs.

#### 🎯 Key Use Cases

- Answer questions using real-time or private data
- Take actions based on contextual input
- Automate end-to-end workflows using AI and tool integrations

#### 🛠️ Features of Azure AI Agent Service

- **Automatic tool invocation** – Models can trigger tools and return results automatically.
- **Secure conversation handling** – Thread-based conversation state management.
- **Pre-built tools** – Includes Bing Search, file search, Azure AI Search, Azure Functions, and more.
- **Flexible model options** – Use Azure OpenAI, Llama 3, Mistral, Cohere, etc.
- **Enterprise-grade security** – Secure, compliant, and keyless authentication.
- **Storage options** – Choose platform-managed or custom Azure Blob storage.

### 🏗️ Develop AI Agents with Azure AI Agent Service

Earlier, creating agent-like behavior required writing extensive code. Now, the Azure AI Agent Service supports **easy integration** using SDKs or REST APIs, with just a few lines of code.

#### 🧠 Knowledge Tools

Used to enhance the agent’s knowledge and ground prompts:

- **Bing Search** – Provides real-time web data.
- **File Search** – Leverages vector stores for file-based content.
- **Azure AI Search** – Queries structured or unstructured datasets.
- **Microsoft Fabric** – Integrates with Fabric Data Agent for contextual enterprise data.

#### ⚡ Action Tools

Used to perform actions or execute functions:

- **Code Interpreter** – Executes model-generated Python code in a sandbox.
- **Function** – Calls your own custom-defined logic.
- **Azure Function** – Executes serverless Azure-hosted code.
- **OpenAPI Spec** – Interacts with external APIs using OpenAPI 3.0 definitions.
---
## 🧩 Module 8 Recap: Integrate Custom Tools into Your AI Agent

### ⚙️ Why Use Custom Tools?

Custom tools in **Azure AI Agent Service** empower developers to tailor agents for specific business needs—improving productivity, accuracy, and process automation.

#### 💡 Benefits of Custom Tools

- **Enhanced Productivity** – Automate repetitive and manual tasks.
- **Improved Accuracy** – Deliver consistent outputs and reduce human error.
- **Tailored Solutions** – Address unique business scenarios with purpose-built tools.

### 🌍 Common Scenarios for Custom Tools

Custom tools allow AI agents to connect with external systems and perform specialized tasks across industries:

#### 🛍️ Customer Support Automation

- **Tool**: Connect to CRM system  
- **Function**: Retrieve orders, process refunds, update shipping  
- **Outcome**: Faster query resolution and improved satisfaction

#### 🏭 Inventory Management

- **Tool**: Link to inventory system  
- **Function**: Monitor stock, predict restocking, place orders  
- **Outcome**: Streamlined operations and efficient supply chain

#### 🏥 Healthcare Scheduling

- **Tool**: Custom scheduling integration  
- **Function**: Suggest slots, access records, send reminders  
- **Outcome**: Better patient experience and reduced admin load

#### 🧑‍💻 IT Helpdesk Support

- **Tool**: Connect to ticketing and knowledge base  
- **Function**: Troubleshoot, escalate, track tickets  
- **Outcome**: Faster issue resolution and improved productivity

#### 🎓 E-Learning and Training

- **Tool**: Connect to LMS  
- **Function**: Recommend courses, track progress, answer queries  
- **Outcome**: Engaged learners and efficient course delivery

### 🔧 Options for Implementing Custom Tools

Azure AI Agent Service supports three main approaches:

#### 🔁 Function Calling

- Dynamically execute custom functions with defined arguments
- Best for integrating logic and workflows directly within your agent
- Language-agnostic and lightweight

#### ⚡ Azure Functions

- Event-driven, serverless execution model
- Use triggers (e.g., HTTP requests) and bindings to connect with other services
- Ideal for real-time, reactive workflows

#### 🌐 OpenAPI Specification Tools

- Connect to external APIs using **OpenAPI 3.0**
- Enables scalable, standardized API integrations
- Helps with code generation, documentation, and design consistency

### 🛠️ How to Integrate Custom Tools

Custom tools can be embedded into your AI agents based on your organizational setup:

#### 🧩 Function Calling

- Add code-defined functions within the agent project
- Great for extending agent logic
- Functions may call other services or APIs internally

#### 🔄 Azure Functions

- Perfect for responding to triggers like message queues or HTTP calls
- Supports lightweight, scalable, and event-based processing

#### 🌐 OpenAPI Tools

- Define tools based on **OpenAPI 3.0 specs**
- Let agents interact with third-party APIs in a standardized way
- Great for automating operations that require external system access
---
## 🧠 Module 9 Recap: Orchestrate a Multi-Agent Solution Using Semantic Kernel
### 🧩 What is the Semantic Kernel Agent Framework?

**Semantic Kernel** is an open-source SDK that helps developers integrate AI models into their applications. Its **Agent Framework** adds capabilities for building intelligent, task-oriented agents that can reason, collaborate, and act autonomously.

#### 🔧 Core Concepts

- **Agents** – Autonomous entities powered by language models, functions, and memory.
- **Agent Collaboration** – Agents can work together using `AgentGroupChat`, enabling back-and-forth communication among specialized agents.
- **Kernel** – Acts as the execution engine for AI interactions and function orchestration.
- **Tools & Plugins** – Allow agents to perform tasks like file search or code execution.
- **History** – Maintains conversation memory for contextual, multi-turn conversations.

#### 🧠 Agent Types Supported

- **AzureAIAgent** – Conversational agent with tool integration and state management.
- **ChatCompletionAgent** – Designed for natural dialogue and chat scenarios.
- **OpenAIAssistantAgent** – Optimized for multi-step, goal-driven interactions.

### 💬 Create a Multi-Agent Group Chat

The **AgentGroupChat** feature enables multiple agents to collaborate dynamically in a shared conversation.

#### 🗨️ Chat Modes

- **Single-turn**: A specific agent is invoked once based on user input.
- **Multi-turn**: Agents take turns responding until a defined termination condition is met.

Messages can be added using the `ChatMessageContent` object, including the sender's role and the message itself.

### 🧠 Design an Agent Selection Strategy

In a multi-agent setup, selecting the right agent is critical for accurate, efficient, and scalable interactions.

#### 🎯 Why Agent Selection Matters

- **Accuracy** – Ensures responses come from domain-relevant agents.
- **Efficiency** – Reduces unnecessary processing and improves response time.
- **Scalability** – Supports larger teams of agents without overwhelming any one.

#### ⚙️ How It Works

- **Single-turn**: Uses intent recognition or developer-defined rules to pick the right agent.
- **Multi-turn**: Tracks context and dynamically switches agents as conversation topics evolve.

> 🔄 Tip: You can **truncate chat history** to reduce token usage and improve performance while retaining the last relevant message for agent selection.

### 🔚 Define a Chat Termination Strategy

To avoid endless conversations, the framework uses a **termination strategy** that determines when the conversation has met its goal.

#### ✅ Why Use a Termination Strategy?

- **Efficiency** – Prevents unnecessary computation and infinite loops.
- **User Satisfaction** – Keeps interactions focused and concise.
- **Goal Clarity** – Signals when a task or workflow has been completed.

Once the chat is marked as **completed**, you’ll need to **reset the state** to allow further use of the `AgentGroupChat` instance.

---
## 📚 References

- [Plan and prepare to develop AI solutions on Azure](https://learn.microsoft.com/en-us/training/modules/prepare-azure-ai-development/?ref=collection&listId=60yka7t2o8od52&sharingId=6A9F03F25E12DA9E&wt.mc_id=aiskillsfest_msftlearn_training_wwl_challenge_tech)  
- [Choose and deploy models from the model catalog in Azure AI Foundry portal](https://learn.microsoft.com/en-us/training/modules/explore-models-azure-ai-studio/?ref=collection&listId=60yka7t2o8od52&sharingId=6A9F03F25E12DA9E&wt.mc_id=aiskillsfest_msftlearn_training_wwl_challenge_tech)
- [Develop an AI app with the Azure AI Foundry SDK](https://learn.microsoft.com/en-us/training/modules/ai-foundry-sdk/?wt.mc_id=challenges_active_registration_confirmation_email_learn)
- [Get started with AI agent development on Azure](https://learn.microsoft.com/en-us/training/modules/ai-agent-fundamentals/?wt.mc_id=challenges_active_registration_confirmation_email_learn)
- [Develop a RAG-based solution with your own data using Azure AI Foundry](https://learn.microsoft.com/en-us/training/modules/build-copilot-ai-studio/?wt.mc_id=challenges_active_registration_confirmation_email_learn)
- [Introduction to AI Agent Service Security Controls](https://learn.microsoft.com/en-us/training/modules/intro-ai-agent-service-security-controls/?wt.mc_id=challenges_active_registration_confirmation_email_learn)
- [Develop an AI agent with Azure AI Agent Service](https://learn.microsoft.com/en-us/training/modules/develop-ai-agent-azure/?wt.mc_id=challenges_active_registration_confirmation_email_learn)
- [Integrate custom tools into your agent](https://learn.microsoft.com/en-us/training/modules/build-agent-with-custom-tools/?wt.mc_id=challenges_active_registration_confirmation_email_learn)
- [Orchestrate a multi-agent solution using Semantic Kernel](https://learn.microsoft.com/en-us/training/modules/orchestrate-semantic-kernel-multi-agent-solution/?wt.mc_id=challenges_active_registration_confirmation_email_learn)
