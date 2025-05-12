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
## 🔄 Creating Your First Prompt Flow: Where the Magic Begins

With your project and model ready, it’s time to build the brain — enter **Prompt Flow**.

Prompt Flow is the visual orchestration layer of Azure AI Foundry. Think of it like a low-code canvas where you connect data, prompts, tools, and Python logic using simple drag-and-drop nodes. It brings structure to your AI agent's thought process — from understanding a question to returning a useful answer.

### 🚀 How to Create a Prompt Flow

Here’s how to get started:

- In your AI Foundry project, go to the **Prompt Flows** tab on the left menu.
- Click **+ Create Flow**.
- Give your flow a name, like `SupportBotFlow`, and click **Create**.

Once created, you’ll be taken to the flow editor — a clean, node-based canvas where all the action happens.

### 🧱 What Comes by Default?

Every new flow starts with three built-in components:

- **Inputs Node**: This defines the parameters your flow will receive (e.g., a `user_query`).
- **Outputs Node**: This defines what your flow returns (e.g., a `response` string).

You’ll see empty start and end points — ready to be wired with **Python nodes**, **LLM nodes**, or other logic blocks to build your agent’s workflow.

### 🛠️ What You Can Add

Prompt Flow supports these key node types:

- **Python Node**: Add your own custom code — for parsing inputs, querying APIs, transforming data, etc.
- **LLM Node**: Drop in a prompt template to invoke the deployed LLM model you chose earlier.

Nodes are connected by **wires**, letting you define how data flows from one step to another — just like a flowchart but smarter.

In the next section, I’ll break down how I created individual nodes for tasks like fetching Jira tickets, summarizing commits, and querying documents — complete with code and LLM prompt examples.

---

## 🧩 Node 1: Fetching GitHub Issue Details (Simulating Jira)

Let’s start by creating our first functional block in the Prompt Flow: a **Python node** to fetch issue data from GitHub. In our POC, this simulates retrieving ticket details from Jira based on a ticket ID like `ABC-123`.

### 🐍 Python Node: `fetch_github_issue`

This node uses GitHub’s API to fetch issue details from a public (or private) repository. We wrap the logic using the `@tool` decorator from Prompt Flow, which lets this function become a reusable node on the canvas.

```python
from promptflow import tool  # 👈 Import this!
import requests

@tool  # 👈 Decorate your function!
def fetch_github_issue(input1: str) -> dict:
    # Construct GitHub API URL
    url = f"https://api.github.com/repos/<>/poc-ai-agent-simulator/issues/{input1}" 

    # Hardcoded GitHub token (for testing only)
    token = "<>"  # 🔁 Replace with your actual GitHub token 

    # Add Authorization header
    headers = {
        "Authorization": f"Bearer {token}",
        "Accept": "application/vnd.github+json"
    }

    # Make the GET request with headers
    response = requests.get(url, headers=headers)

    # Parse JSON response
    data = response.json()

    return {
        "title": data.get("title", "No title found"),
        "body": data.get("body", "No body found")
    }
  ```
  📝 Note: Replace the <> placeholders with your actual GitHub repo path and GitHub token for local testing. In production or shared environments, never hardcode tokens — use Key Vault or environment variables instead.

### 🔗 Node Input
This node expects a single input:

input1 — the GitHub issue number to fetch
Example: ${parse_router_output.output.query}

### 🤖 LLM Node: generate_response
Now that we’ve fetched issue data, we pass it to a LLM node to generate a user-friendly response. This node connects to our previously deployed gpt-4o model and uses a system + user prompt combination.

```
system:
You are a helpful assistant.

user:
Based on the following GitHub Issue details:

Title: {{ title }}
Body: {{ body }}

**Instructions:**
- Base your summary strictly on the title and body content.
- Do not assume additional issue context or status.
- If either title or body is missing or unclear, ask for clarification.
```

### 🔌 Node Configuration

| **Setting**         | **Value**                                             |
|---------------------|-------------------------------------------------------|
| Connection          | `ai-pocaiagentsimulatorhub813931831613_aoai`          |
| API Type            | `chat`                                                |
| Deployment Name     | `gpt-4o`                                              |
| Temperature         | `1`                                                   |
| Max Tokens          | *(default or custom)*                                 |
| Stop                | *(optional)*                                          |
| Response Format     | `{"type":"text"}`                                     |

### 🔁 LLM Input Mapping

| **LLM Prompt Variable** | **Mapped From**                             |
|-------------------------|---------------------------------------------|
| `title`                 | `${fetch_github_issue.output.title}`        |
| `body`                  | `${fetch_github_issue.output.body}`         |

Together, these two nodes simulate the first core functionality of our assistant: **understanding a ticket ID and summarizing its issue details clearly** using real-time API data and GPT.

---

## 🧩 Node 2: Fetching and Summarizing Git Commits (Simulating GitLab History)

After retrieving issue details, the next step is to trace the commit history related to that ticket. In this node, we simulate GitLab commits by fetching recent GitHub commits and filtering them by the ticket ID found in commit messages.

### 🐍 Python Node: `fetch_github_commits`

This Python node queries GitHub’s Commits API, filters the results for any commit message containing the ticket ID, and returns a structured list.

```python
from promptflow import tool
import requests

@tool
def fetch_github_commits(ticket_query: str) -> list:
    # Hardcoded GitHub token for now
    token = "<>"  # Replace for production 

    # GitHub API URL
    url = "https://api.github.com/repos/<>/poc-ai-agent-simulator/commits" 
    headers = {
        "Authorization": f"Bearer {token}",
        "Accept": "application/vnd.github+json"
    }

    params = {
        "per_page": 10  # limit results
    }

    response = requests.get(url, headers=headers, params=params)
    commits = response.json()

    matched_commits = []

    if not isinstance(commits, list):
        print("GitHub API error:", commits)
        return []

    for commit in commits:
        message = commit.get("commit", {}).get("message", "")
        print("Checking commit:", message)  # Debug log

        if ticket_query.lower() in message.lower():
            matched_commits.append({
                "message": message,
                "date": commit.get("commit", {}).get("author", {}).get("date", ""),
                "url": commit.get("html_url", "")
            })

    print("Matched commits:", matched_commits)  # Final debug output
    return matched_commits
```
> 🔒 **Tip:** As before, replace `<token>` and the `<repo>` placeholder with valid values during local testing. Avoid hardcoding secrets in production environments. Use Key Vault or environment variables for secure handling.

### 🔗 Node Input

- **ticket_query** — the same ticket ID used earlier  
  Example: `${parse_router_output.output.query}`


### 🤖 LLM Node: `summarize_commits`

This LLM node takes the filtered list of commits and turns them into a concise, human-readable summary. It uses a templated prompt to stay focused strictly on the available data.

**Prompt Template:**

```jinja2
system:
You are an assistant summarizing Git commit history related to a ticket.

user:
Query: {{ ticket_query }}

Here are the commits retrieved:

{% for commit in commits %}
- {{ commit.message }}
{% endfor %}

**Instructions:**
- Summarize only the commit messages shown above.
- Do not infer or imagine commits not listed.
- If the list is empty or unclear, respond accordingly.
```

### 🔁 LLM Input Mapping

| **LLM Prompt Variable** | **Mapped From**                      |
|-------------------------|--------------------------------------|
| `commits`               | `${fetch_github_commits.output}`     |
| `ticket_query`          | `${parse_router_output.output}`      |

This completes the second major task of our AI assistant: **retrieving and summarizing Git commit history tied to a specific ticket** — a common requirement in any agile DevOps workflow.

---

## 🧩 Node 3: Searching Confluence-Like Docs from GitHub

Our next step simulates a search across internal documentation — similar to browsing Confluence pages. In this POC, we're using markdown files stored in a GitHub `/docs` folder as a substitute.

### 🐍 Python Node: `search_confluence_docs`

This Python node scans markdown files in a specified GitHub repo folder and checks if any contain the `ticket_query` keyword. It returns the matching file names and a short excerpt from each file's content.

```python
from promptflow import tool
import requests

@tool
def search_confluence_docs(ticket_query: str) -> list:
    token = "<>"  # 🔁 Replace with your actual token 
    repo = "<>/poc-ai-agent-simulator" 
    folder_path = "docs"
    
    headers = {
        "Authorization": f"Bearer {token}",
        "Accept": "application/vnd.github+json"
    }

    # 1. List files in the docs folder
    url = f"https://api.github.com/repos/{repo}/contents/{folder_path}"
    response = requests.get(url, headers=headers)
    files = response.json()

    results = []
    keyword = ticket_query.lower()

    for file in files:
        if file["name"].endswith(".md"):
            raw_url = file["download_url"]
            content_response = requests.get(raw_url)
            content = content_response.text.lower()
            if keyword in content:
                results.append({
                    "filename": file["name"],
                    "excerpt": content[:300]
                })

    return results
```
> 🔒 **Tip:** Use environment variables or a secret store like **Azure Key Vault** to manage tokens securely in production.

### 🔗 Node Input

- **ticket_query** — passed directly from the user’s query  
  Example: `${parse_router_output.output.query}`

### 🤖 LLM Node: `summarize_confluence_search`

This node takes the search results and uses an LLM to summarize the most relevant information. It also suggests which documents to explore further — without hallucinating any extra content.

**Prompt Template:**

```jinja2
system:
You are an expert assistant specializing in knowledge management and document retrieval.

user:
The user is investigating Confluence documentation related to: **{{ ticket_query }}**

Here are the excerpts found from the search results:

{% for doc in search_confluence_docs %}
- **File**: {{ doc.filename }}
- **Excerpt**: "{{ doc.excerpt }}"
{% endfor %}

**Instructions:**
- Summarize the key information found across these documents.
- Highlight which documents seem most relevant.
- Suggest if any document should be reviewed in more detail.
- Only refer to the excerpts shown above.
- Do not assume or create content not present in the listed files.
- If the list is empty, respond by stating no relevant documents were found.

### 🔁 LLM Input Mapping

| **LLM Prompt Variable**     | **Mapped From**                                |
|-----------------------------|------------------------------------------------|
| `search_confluence_docs`    | `${search_confluence_docs.output}`             |
| `ticket_query`              | `${parse_router_output.output.query}`          |

With this step, the assistant gains the ability to **search and summarize relevant documentation** — helping users discover insights hidden in internal knowledge bases without ever leaving the chat.

---

## 🧩 Node 4: Searching SharePoint-Like Docs in Azure Blob Storage

The final key workflow in our POC is simulating SharePoint document search. In the real world, SharePoint often stores SOPs, team guides, and process documents. For this prototype, we emulate that by using plain `.txt` files stored in **Azure Blob Storage**.

### 🐍 Python Node: `search_sharepoint_docs`

This node connects to an Azure Blob Storage container, reads `.txt` files, and checks for content that matches the user’s query. If a match is found, it returns the file name and a short excerpt.

```python
from promptflow import tool
from azure.storage.blob import BlobServiceClient
import io

@tool
def search_sharepoint_docs(ticket_query: str) -> list:
    connection_string = "DefaultEndpointsProtocol=https;AccountName=<>;AccountKey=<>==;EndpointSuffix=core.windows.net" 
    container_name = "documents"

    blob_service_client = BlobServiceClient.from_connection_string(connection_string)
    container_client = blob_service_client.get_container_client(container_name)

    results = []
    keyword = ticket_query.lower()

    for blob in container_client.list_blobs():
        if not blob.name.endswith(".txt"):
            continue  # Only process .txt files

        blob_client = container_client.get_blob_client(blob)
        blob_data = blob_client.download_blob().readall()
        content = blob_data.decode("utf-8").lower()

        if keyword in content:
            results.append({
                "filename": blob.name,
                "excerpt": content[:300]
            })

    return results
```

> 🔒 **Tip:** Always use **Azure Key Vault** or secure environment variables for managing your Blob Storage connection string. Avoid hardcoding secrets in your code.

### 🔗 Node Input

- **ticket_query** — same query passed from earlier  
  Example: `${parse_router_output.output.query}`

### 🤖 LLM Node: `summarize_sharepoint_docs`

This LLM node processes the output of our Blob Storage document search and summarizes the most relevant content — just like an AI assistant browsing SharePoint for you.

**Prompt Template:**

```jinja2
system:
You are an expert assistant specializing in knowledge management and document retrieval.

user:
The user is investigating SharePoint documents for the topic or ticket: **{{ ticket_query }}**.

Here are the excerpts found from the search results:

{% for doc in search_sharepoint_docs %}
- **File**: {{ doc.filename }}
- **Excerpt**: "{{ doc.excerpt }}"
{% endfor %}

**Instructions:**
- Only reference and summarize the content of the documents listed above.
- Do not invent or assume the existence of additional documents.
- If only one document is listed, summarize only that one.
- If no documents are listed, say "No relevant documents were found."

```

### 🔁 LLM Input Mapping

| **LLM Prompt Variable**     | **Mapped From**                                |
|-----------------------------|------------------------------------------------|
| `search_sharepoint_docs`    | `${search_sharepoint_docs.output}`             |
| `ticket_query`              | `${parse_router_output.output}`                |

---

## 🧩 Node 5: Smart Routing with `router_llm`

Before any task-specific nodes are triggered, we need a way to **understand user intent** and route the query to the correct internal tool — whether that’s fetching an issue, summarizing commits, or searching documents.

That’s the role of the `router_llm` node: a lightweight, intelligent router that interprets user queries and decides **which downstream tool** should handle the request.

### 🤖 LLM Node: `router_llm`

This LLM node uses a prompt that defines available tools and their purpose. Based on the user’s input, it returns a clean JSON response specifying:

- `tool`: which tool should be used (`GetGitHubIssue`, `GetCommitsForTicket`, etc.)
- `query`: the value extracted from the user input (e.g., `ABC-123`, `#25`, or a natural-language search string)

**Prompt Template:**

```jinja2
system:
You are a router assistant. Your job is to decide which internal tool to use based on the user's input.

Available tools:
- GetGitHubIssue → used **only** when the user asks about GitHub **issue number** (like `#23`, `issue 5`, etc.)
- GetCommitsForTicket → used when the user asks about a **ticket ID** or task reference like `ABC-123` that appears in commit messages
- SearchConfluenceDocs → used when the user asks for internal documentation
- SearchSharePointDocs → used when the user wants files, guides, PDFs, or SOPs from storage
- HandleChitChat → used when the user is making casual conversation, greetings, jokes, or unrelated questions

Respond only with **raw JSON**. Do **not** include markdown, formatting, or explanations. The response must be exactly like:
{
  "tool": "<tool_name>",
  "query": "<the relevant value extracted from user query>"
}

For HandleChitChat, return the full user query as the `query` value.

user:
{{ user_query }}
```

#### 🔗 Node Input

- **user_query** — the original raw input from the user  
  Example: `${inputs.ticket_query}`

This routing step is what makes the assistant **agentic** — it dynamically decides what action to take based on user intent, instead of relying on rigid input types or menus.

---

## 🧩 Node 6: Formatting the Final Response for the User

Once the right tool has done its job — whether it’s fetching a GitHub issue, summarizing commits, or searching documents — we need to format the final response in a clean and user-friendly way.

That’s where the **`final_response_formatter`** node comes in. This node acts like the **final narrator** of your AI assistant, intelligently choosing which tool's output to present and formatting it with appropriate context.

### 🤖 LLM Node: `final_response_formatter`

This LLM node receives output from all possible downstream tools and decides what to show back to the user, using conditional logic in the prompt.

**Prompt Template:**

```jinja2
system:
You are a summarizer assistant that returns the final result from the selected tool. Based on the user’s query, one of the tools has returned a relevant response.

user:
{% if generate_response %}
### 🔍 Direct Answer  
{{ generate_response }}

{% elif summarize_commits %}
### 📌 GitHub Commits Summary  
{{ summarize_commits }}

{% elif summarize_confluence_search %}
### 📘 Confluence Document Summary  
{{ summarize_confluence_search }}

{% elif summarize_sharepoint_docs %}
### 📁 SharePoint Document Summary  
{{ summarize_sharepoint_docs }}

{% elif handle_chitchat %}
### 💬 Friendly Chat  
{{ handle_chitchat }}

{% else %}
❗ No relevant response was generated by any tool. Please try rephrasing your query.
{% endif %}
```

This prompt ensures only one result is displayed at a time and labels the response for clarity — giving users an easy-to-read, conversational summary.

### 🔁 LLM Input Mapping

| **LLM Prompt Variable**         | **Mapped From**                                |
|---------------------------------|------------------------------------------------|
| `generate_response`             | `${generate_response.output}`                  |
| `handle_chitchat`               | `${handle_chitchat.output}`                    |
| `summarize_commits`             | `${summarize_commits.output}`                  |
| `summarize_confluence_search`   | `${summarize_confluence_search.output}`        |
| `summarize_sharepoint_docs`     | `${summarize_sharepoint_docs.output}`          |

This is the **final step** in the flow — where everything comes together. The assistant picks the most appropriate response, wraps it with a contextual heading, and speaks back in a friendly, organized format.

---

## 🧩 Node 7: Parsing the Router Output

The `router_llm` node returns a JSON response that tells the assistant which internal tool to use and what query value to pass. However, because LLMs sometimes return their output wrapped in code blocks (like ```json), we need a small parser to clean and validate this output before routing it further.

That’s exactly what the **`parse_router_output`** Python node does — it acts as a **sanity check and cleanup utility** between the router and the rest of the flow.

### 🐍 Python Node: `parse_router_output`

This node takes the raw string output from `router_llm`, removes any Markdown-style code fences (like ```json), and converts it into a clean Python dictionary with two keys: `tool` and `query`.

```python
from promptflow import tool
import json

@tool
def parse_router_output(router_llm_output: str) -> dict:
    try:
        # Clean up markdown-style code block if present
        cleaned = router_llm_output.strip()
        if cleaned.startswith("```json"):
            cleaned = cleaned.removeprefix("```json").removesuffix("```").strip()
        elif cleaned.startswith("```"):
            cleaned = cleaned.removeprefix("```").removesuffix("```").strip()

        # Parse the cleaned string as JSON
        data = json.loads(cleaned)
        return {
            "tool": data.get("tool", ""),
            "query": data.get("query", "")
        }
    except Exception as e:
        return {
            "tool": "",
            "query": f"ERROR: {str(e)}"
        }
```

### 🔗 Node Input

- **router_llm_output** — the raw JSON response string from the router LLM  
  Example: `${router_llm.output}`

This parser makes your flow more **robust and production-ready**, handling common formatting quirks from LLMs and ensuring downstream nodes get clean, structured input to work with.

---

## 🧩 Node 8: Handling Casual Chat with `handle_chitchat`

Not every user message will be a technical query. Sometimes users will say things like *"Hi there!"*, *"How’s your day?"*, or even crack a joke. These don’t need to be routed to a tool or data source — they just need a friendly, human-like response.

That’s where the **`handle_chitchat`** node comes in. This LLM node is activated when the router detects casual conversation, jokes, or greetings. It ensures the assistant feels warm, interactive, and approachable — just like a real human teammate.

### 🤖 LLM Node: `handle_chitchat`

This node uses a lightweight prompt designed for friendly back-and-forth interactions. It doesn’t pull from any data sources — it simply replies based on tone and intent.

**Prompt Template:**

```jinja2
system:
You are a friendly and engaging assistant that handles casual conversations, greetings, and small talk.

user:
{{ message }}
```

### 🔗 Node Input

- **message** — extracted from the router output query  
  Example: `${parse_router_output.output.query}`

### ⚙️ Activation Condition

This node is **only triggered when** the router returns `"HandleChitChat"` as the tool name:

```text
When ${parse_router_output.output.query} is HandleChitChat
```
This keeps your assistant **responsive and personable** — creating a better user experience even when the conversation isn’t about Jira tickets or documentation.

---

## 🚀 Deploying the Model with an Azure ML Endpoint

Once your model is selected and tested in Prompt Flow, the final step is to **expose it via a RESTful API** so external apps or scripts can query it. Azure AI Foundry makes this easy by letting you deploy to a **Managed Online Endpoint (ML Endpoint)**.

### 🧭 Steps to Deploy via ML Endpoint

1. In your Azure AI Foundry project, go to the **Deployments** tab.
2. Choose your model (e.g., `gpt-4o`) from the list.
3. Click **Deploy** and select:
   - **Deployment type**: Managed Online Endpoint
   - **Version updates**: Enabled (optional)
   - **Rate limit**: Set as per your token quota (e.g., 50K TPM)

Once the deployment is complete, you’ll see an **Endpoint Name** listed.

### 🔑 Retrieve Endpoint Info

After deployment, go to the **ML Studio** or use the Azure CLI/portal to fetch:

- **Scoring URL**
- **API Key**

From ML Studio:

- Navigate to the deployed endpoint
- Click on **Consume**
- Copy the **Scoring URL** and **Primary Key**

### 🧪 Test with `curl`

Here’s a simple `curl` command to test the deployed model using the scoring endpoint:

```bash
curl -X POST <YOUR_SCORE_URL> \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer <YOUR_API_KEY>" \
  -d '{
    "inputs": {
      "user_query": "What is the status of ticket ABC-123?"
    }
  }'
```

> 🔁 **Replace** `<YOUR_SCORE_URL>` and `<YOUR_API_KEY>` with the actual values from your ML deployment.

### ✅ Expected Output

The response will include the model's output (summary, commit analysis, document search, or chat) in JSON format, depending on what path the router selected internally.

This is how you can **expose your Prompt Flow-based agent as a public REST API**, ready to integrate with web apps, bots, or automation tools.
