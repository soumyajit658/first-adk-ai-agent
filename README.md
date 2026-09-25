# 🤖 My First Google ADK AI Agent

My first AI agent built using **Google's Agent Development Kit (ADK)** and **Gemini**.

This project was created while learning the fundamentals of building, configuring, running, and interacting with an AI agent using Google's ADK.

---

## 📌 Project Overview

This project contains a simple AI assistant created with Google ADK.

The agent uses a Gemini model as its underlying language model and is configured with an instruction that tells it to answer user questions.

The project was created as my first practical introduction to:

- Google Agent Development Kit (ADK)
- Gemini models
- AI agents
- Agent instructions
- Python virtual environments
- Environment variables
- ADK CLI
- ADK Web UI
- Git and GitHub

---

# 🧠 What is Google ADK?

**Google Agent Development Kit (ADK)** is a framework for building AI agents.

Instead of only creating a simple chatbot, ADK provides tools and structures for building agents that can eventually:

- Use tools
- Call APIs
- Work with external data
- Execute multi-step workflows
- Interact with other agents
- Perform actions based on user requests

This project is a beginner-level starting point before moving toward more advanced agentic applications.

---

# 🏗️ Current Agent Architecture

The current agent is intentionally simple.

```text
                    ┌─────────────────┐
                    │      User       │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │   Google ADK   │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │   root_agent   │
                    │                 │
                    │  Instructions   │
                    │  Description    │
                    │  Gemini Model   │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │     Gemini      │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │    Response     │
                    └─────────────────┘
```

---

# 🛠️ Technologies Used

- **Python**
- **Google ADK**
- **Gemini**
- **Google AI**
- **Git**
- **GitHub**
- **VS Code**

---

# 📂 Project Structure

```text
First-Ai-Agent-ADK/
│
├── .venv/
│   └── Python virtual environment
│
├── my_agent/
│   ├── .env
│   ├── .gitignore
│   ├── __init__.py
│   └── agent.py
│
├── README.md
└── .gitignore
```

## File and Folder Explanation

### `.venv/`

Python virtual environment used for this project.

It keeps the project's Python packages isolated from other Python projects on the computer.

Installed packages are stored inside the virtual environment rather than directly in the project source code.

---

### `my_agent/`

The main ADK application.

This directory contains the files needed for the AI agent.

---

### `my_agent/agent.py`

The main Python file containing the root ADK agent.

Current implementation:

```python
from google.adk.agents.llm_agent import Agent

root_agent = Agent(
    model='gemini-3.5-flash',
    name='root_agent',
    description='A helpful assistant for user questions.',
    instruction='Answer user questions to the best of your knowledge',
)
```

### Explanation

#### Importing the Agent

```python
from google.adk.agents.llm_agent import Agent
```

Imports the `Agent` class from Google ADK.

---

#### Creating the root agent

```python
root_agent = Agent(
```

Creates the main/root agent used by the application.

---

#### Model

```python
model='gemini-3.5-flash',
```

Specifies the Gemini model used by the agent.

---

#### Name

```python
name='root_agent',
```

Defines the internal name of the root agent.

---

#### Description

```python
description='A helpful assistant for user questions.',
```

Describes the purpose of the agent.

---

#### Instruction

```python
instruction='Answer user questions to the best of your knowledge',
```

Defines how the agent should behave when responding to users.

---

### `my_agent/.env`

Contains sensitive configuration such as the Google API key.

Example:

```text
GOOGLE_API_KEY=YOUR_API_KEY
```

**The real API key is NOT stored in this GitHub repository.**

The `.env` file must remain private.

---

### `my_agent/.gitignore`

Used to prevent sensitive files such as `.env` from being committed to Git.

Example:

```gitignore
.env
```

---

### `my_agent/__init__.py`

Python package initialization file used by the ADK application structure.

---

### `.gitignore`

The project-level Git ignore file should prevent the virtual environment, secrets, Python cache files, and other generated files from being committed.

Recommended contents:

```gitignore
.venv/
.env
__pycache__/
*.pyc
```

---

# ⚙️ Setup

## 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/first-adk-ai-agent.git
```

Enter the project:

```bash
cd first-adk-ai-agent
```

---

# 🐍 2. Create a virtual environment

Windows PowerShell:

```powershell
python -m venv .venv
```

---

# ▶️ 3. Activate the virtual environment

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

After activation, the terminal should show:

```text
(.venv)
```

---

# 📦 4. Install Google ADK

```powershell
python -m pip install google-adk
```

Check the installation:

```powershell
adk --version
```

Example:

```text
adk, version 2.9.2
```

---

# 🔑 5. Configure the Gemini API key

The agent requires a Google API key.

Create an API key through Google AI Studio.

Do **not** put your actual API key inside this README or any public GitHub file.

Store the key in the local `.env` file.

Example:

```text
GOOGLE_API_KEY=YOUR_API_KEY
```

Replace `YOUR_API_KEY` with your actual local API key.

---

# 🚀 Creating an ADK Agent

A new ADK application can be created using:

```powershell
adk create my_agent
```

During creation, ADK asks for configuration such as:

- Gemini model
- Backend
- Google API key

After creation, the basic application contains:

```text
my_agent/
├── .env
├── .gitignore
├── __init__.py
└── agent.py
```

---

# 🖥️ Running the Agent

## Run from the terminal

```powershell
adk run my_agent
```

This provides a terminal-based interface for interacting with the agent.

Example:

```text
You: Hello! Who are you?
Agent: ...
```

---

# 🌐 Running the ADK Web UI

The ADK Web UI can be started with:

```powershell
adk web my_agent
```

ADK starts a local web server.

Open the displayed local URL in a browser such as Chrome.

The architecture becomes:

```text
Chrome
   │
   ▼
ADK Web UI
   │
   ▼
root_agent
   │
   ▼
Gemini
   │
   ▼
Response
```

To stop the server:

```text
Ctrl + C
```

---

# 🧰 Useful ADK Commands

## Check ADK version

```powershell
adk --version
```

## Display help

```powershell
adk --help
```

## Create an application

```powershell
adk create my_agent
```

## Run an agent in the terminal

```powershell
adk run my_agent
```

## Run the ADK Web UI

```powershell
adk web my_agent
```

Other ADK commands include:

```text
api_server
conformance
deploy
eval
eval_set
migrate
optimize
telemetry
test
web
```

---

# 🔐 Security

API keys and other secrets should never be committed to GitHub.

The following should remain private:

```text
.env
```

The virtual environment should also not be uploaded:

```text
.venv/
```

Recommended `.gitignore`:

```gitignore
.venv/
.env
__pycache__/
*.pyc
```

Before pushing to GitHub, always check:

```powershell
git status
```

Make sure your API key is not included in the files being committed.

---

# 📚 What I Learned

Through this project, I learned the basic workflow for creating an AI agent with Google ADK:

1. Create a Python project.
2. Create and activate a virtual environment.
3. Install Google ADK.
4. Verify the ADK CLI.
5. Create an ADK application.
6. Configure a Gemini model.
7. Configure a Google API key.
8. Create a root agent.
9. Define the agent's name and description.
10. Define the agent's instructions.
11. Run the agent through the ADK CLI.
12. Run the agent through the ADK Web UI.
13. Use Git to version-control the project.
14. Prepare the project for GitHub.

---

# 🔮 Future Improvements

This is only the beginning.

Future versions of this project can include:

- Custom Python tools
- API integrations
- Database integration
- Firebase
- Multiple agents
- Agent-to-agent communication
- Function/tool calling
- External data sources
- Authentication
- React frontend
- Backend API
- Deployment to Google Cloud
- More advanced agent workflows

The next major learning step is to give the agent **custom tools** so that it can perform actions rather than only generate responses.

Example future architecture:

```text
                         ┌── Weather API
                         │
                         ├── Database
                         │
User → AI Agent ─────────┼── Calculator
                         │
                         ├── Search/API
                         │
                         └── Custom Python Tool
```

---

# 🎯 Goal

The goal of this project is to progress from a simple Gemini-powered assistant toward a complete AI agent capable of reasoning, using tools, accessing data, and performing useful tasks.

This repository represents my **first step into AI agent development with Google ADK**.

---

# 👨‍💻 Author

**Your Name**

GitHub:

`https://github.com/YOUR_USERNAME`

---

# ⭐ Acknowledgements

Built while learning Google's **Agent Development Kit (ADK)** and Gemini.

---

## ⚠️ Disclaimer

This is a beginner learning project created for educational purposes.
