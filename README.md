# 🤖 Personal AI Multi Agent Assistant

A modular multi-agent assistant built with **n8n** that processes **text and voice requests**, intelligently routes tasks to specialized agents, and executes actions across email, calendar, research, and support domains. Designed for scalability, contextual understanding, and practical productivity.

---

## 📸 Workflow Overview

Workflow screenshots:

![Workflow Diagram](Assets/ai_personal_assistant_main_workflow.png?raw=true "AI multi-agent-assistant Screenshot")

![Workflow Diagram](Assets/ai_personal_assistant_calendar_agent.png?raw=true "AI multi-agent-assistant Screenshot")

![Workflow Diagram](Assets/ai_personal_assistant_crm_agent.png?raw=true "AI multi-agent-assistant Screenshot")

![Workflow Diagram](Assets/ai_personal_assistant_email_agent.png?raw=true "AI multi-agent-assistant Screenshot")

![Workflow Diagram](Assets/ai_personal_assistant_research_agent.png?raw=true "AI multi-agent-assistant Screenshot")

---

## 🧠 Core Architecture

The system consists of two key layers:

### 1. **Main Agent (Orchestrator)**
- Processes incoming **Telegram messages** (text or audio)
- Converts voice to text
- Analyzes user intent using AI models (e.g., Gemini or OpenAI)
- Identifies **single or composite requests** and routes them to appropriate child agents

### 2. **Child Agents (Modular Workflows)**
Each child agent is an independent workflow for specific tasks. The main agent activates them as needed.

---

## 🧩 Child Agent Descriptions

### 📧 Email Agent
- Validates recipient contacts using a **Google Sheets database**
- Composes and sends emails with AI-generated content
- Supports dynamic subjects, message bodies, and optional reminders
- Can be extended for attachments, CC/BCC, and templates

**Example Query**:
> "Send John an email confirming meeting details."

---

### 📅 Calendar Agent
- Schedules events and meetings with **timezone awareness**
- Validates participants through contact database unless explicitly provided
- Can be extended for recurring events, reminders, and synchronization

**Example Query**:
> "Schedule a call with Sarah next Tuesday at 3 PM."

---

### 🛠️ Customer Support Agent (RAG)
- Uses **Retrieval-Augmented Generation** to answer questions
- Pulls information from knowledge base (FAQs, documentation)
- Ensures accurate responses **without hallucinations**
- Responses are delivered unaltered for reliability

**Example Query**:
> "What is the refund policy for premium users?"

---

### 🔍 Research Agent
- Performs online searches based on user queries
- Provides concise relevant insights with sources
- Can be extended for deeper analysis and reports

**Example Query**:
> "Find top 3 AI workflow tools in 2025."

---

## 🛠️ Technology Stack

- **n8n** – Workflow orchestration
- **Telegram Bot** – Request channel (text + voice)
- **OpenAI / Gemini** – Intent analysis and agent logic
- **Google Sheets** – Contact database
- **Gmail / Calendar API** – Action execution
- **RAG Stack** – Knowledge retrieval for support
- **Web Search API** – Research backend

---

## 🎯 Use Cases

- Personal productivity assistant
- AI-powered customer support bot
- Internal team assistant
- Scalable platform for enterprise automation

---

## 📌 Notes

- The system is **modular** - new agents can be added without core changes
- Voice requests are processed like text
- Contact validation ensures task execution accuracy
- RAG agent responses are based on source materials without alterations

