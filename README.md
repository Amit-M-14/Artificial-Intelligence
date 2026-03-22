# 🤖 AI Executive Assistant (n8n + OpenRouter)

A powerful autonomous AI agent built in **n8n** that manages data, schedules, and communication. It uses **Llama (via NVIDIA/OpenRouter)** for reasoning and connects to the Google Workspace ecosystem.

## 🚀 Overview

This agent is designed to handle common administrative tasks through a simple chat interface. It can retrieve user data, manage a calendar, and send professional emails automatically.

### Key Features
* **Brain:** Powered by `NVIDIA Llama` via **OpenRouter** (cost-effective alternative to GPT-4).
* **Memory:** Integrated `Simple Memory` buffer (stores the last 5 interactions for context).
* **Data Management:** Reads and writes to **Google Sheets** for user information (Name, Email, etc.).
* **Scheduling:** Automatically creates and manages events in **Google Calendar**.
* **Messaging:** Sends automated responses or notifications via **Gmail**.

---

## 🛠️ Tech Stack

* **Workflow Engine:** [n8n.io](https://n8n.io/)
* **LLM Provider:** OpenRouter (NVIDIA Llama Model)
* **Memory:** Simple Window Memory (Limit: 5)
* **Integrations:** * Google Sheets API
    * Google Calendar API
    * Gmail API

---

## 📋 How to Use

1.  **Import the Workflow:**
    * Download the `.json` file from this repository.
    * Open your n8n instance and select **Import from File**.
2.  **Setup Credentials:**
    * Add your **OpenRouter API Key** in the AI Agent node.
    * Authenticate your **Google Cloud Console** credentials for Sheets, Calendar, and Gmail nodes.
3.  **Configure the Sheet:**
    * Ensure your Google Sheet has headers for `Name` and `Email` (or update the node mappings in n8n).
4.  **Execute:**
    * Start the **Chat Trigger** and begin interacting with your agent!

---

## ⚙️ Workflow Logic
1.  **Chat Trigger:** Receives the user prompt.
2.  **AI Agent Node:** Processes the intent using Llama.
3.  **Tool Selection:**
    * If the user asks "Who is [Name]?", the agent queries **Google Sheets**.
    * If the user asks to "Book a meeting," the agent uses **Google Calendar**.
    * If a confirmation is needed, the agent triggers **Gmail**.
4.  **Memory:** Ensures the agent remembers the user's name or the previous question within a 5-turn window.

---

*Developed with ❤️ using n8n and OpenRouter.*
