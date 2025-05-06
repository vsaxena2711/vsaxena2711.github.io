---
title: "🧠🚀 Meet Azure AI Foundry’s Magic. Drag. Drop. Deploy. REPEAT"
date: 2025-05-05
draft: true
categories: ["AI-nstein's Notebook"]
tags: ["Azure AI Foundry", "Prompt Flow", "Agentic AI", "Low Code AI", "Microsoft AI"]
description: "Explore how Azure AI Foundry makes it insanely easy to go from idea to AI with its drag-and-drop Prompt Flow interface. No fluff. Just flow."
---

> *Like Remy the rat in **Ratatouille** — **"Anyone can Cook"**.*  
> *With Azure AI Foundry, anyone can build AI. Just drag, drop, and let the bot cook.* 👨‍🍳🤖

Welcome to the world of **Azure AI Foundry**, where **Prompt Flow** makes AI development feel less like programming and more like storytelling. Whether you're an AI newbie or a seasoned dev, this platform strips away the noise and lets you focus on building **agentic solutions** with clarity and speed.

In this post, I’ll walk you through how I used Azure AI Foundry to create a working AI bot using **Prompt Flow**, including:

- The magic behind the drag-and-drop experience 🎨  
- Connecting tools, prompts, and data without writing heavy code 🔌  
- Deploying it all with ML Endpoints — no dev-ops chaos 🔧  
- Lessons learned and what’s next on this AI journey 🔄  
---
## 🧩 Use Case: What This Bot Actually Does

Before we dive into building, let’s talk about the **"why"**. This POC simulates a unified chatbot assistant designed to support multiple enterprise workflows through natural language — turning scattered systems into one seamless AI-driven interface.

### 🧠 Business Use Cases

The bot is built to understand and act on the following types of queries:

- **GetJiraTicket**: Retrieve ticket details based on a Jira-style ID (e.g., `ABC-123`).
- **GetCommitsForTicket**: Fetch Git commits associated with a specific ticket ID.
- **SearchConfluenceDocs**: Look through internal documentation (like Confluence) using natural-language search.
- **SearchSharePointDocs**: Find SharePoint-stored SOPs or internal guides based on keywords.

### 🧪 Simulated Environment Setup

Since real enterprise tools weren’t available for this demo, we simulated them using accessible public resources:

| Real Tool             | Simulated Using                          |
|-------------------    |-------------------------------------------|
| Jira Tickets          | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;GitHub Issues                            |
| GitLab Commits        | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;GitHub Commits API                       |
| Confluence Docs       | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;GitHub Markdown Files (`/docs` folder)   |
| SharePoint Docs       | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Azure Blob Storage with public `.txt` files |

This setup lets us test core logic and integration patterns without exposing real production data — perfect for a secure and cost-effective POC.

---

Next, let’s explore how you can build this out yourself using Azure AI Foundry.

---
## 🛠️ Getting Started: From Zero to AI Hero with Azure AI Foundry

If you're brand new to **Azure AI Foundry**, this is your launchpad. Follow these steps to create your first project, explore available models, and deploy one — all inside the Foundry portal.


### 1️⃣ Set Up Your AI Workspace

Your journey starts with an **AI hub** — a collaborative space that houses one or more projects.

- Open [https://ai.azure.com](https://ai.azure.com) and sign in with your Azure credentials.
- Close any welcome messages or side panels that pop up.
- Click on **+ Create project**.
- In the wizard:
  - Give your project a name.
  - Choose to **create a new hub** if prompted.
- Click **Customize**, and then provide:
  - **Hub Name**
  - **Subscription**: Select your Azure subscription
  - **Resource Group**: Create or pick one
  - **Location**: Click **Help me choose**, select `gpt-4o`, and follow the region recommendation
  - **Connect AI Services**: Create a new Azure AI resource
  - **AI Search**: Skip it for now

Hit **Next**, review your setup, and then click **Create**. Once it’s ready, close any tips and explore your project space.


### 2️⃣ Explore Models with Built-In Benchmarks

Foundry offers a **Model Catalog** to help you find the right model through specs and benchmark scores.

- In the left menu, click **Model Catalog**.
- Search for `gpt-4o` and click on the model name.
- Review the **description** and switch to the **Benchmarks** tab for comparison insights.
- Use the back arrow to return to the catalog.
- Now search for `phi-3.5-mini-instruct` and check its details too.

This quick compare helps you pick the best-fit model for your use case.


### 3️⃣ Deploy a Model (Without the Headaches)

Once you've found your model, you're ready to deploy. Here's how to do it directly from the catalog:

- From the catalog, select `gpt-4o` again.
- Click **Deploy**, then choose **Customize**.
- Fill in the deployment settings:
  - **Deployment Name**
  - **Type**: Global Standard
  - **Version Updates**: Enable automatic updates
  - **Model Version**: Pick the latest one
  - **Connected Resource**: Use your Azure OpenAI connection
  - **TPM (Tokens per Minute)**: Set to 50K or your max available
  - **Content Filter**: DefaultV2

Click **Deploy** and wait for it to finish. That’s it — your model is now live and ready to use!

---

