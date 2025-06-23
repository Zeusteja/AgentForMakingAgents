# AgentForge: The Agent That Builds Agents

AgentForge is a generative automation system designed to turn natural language prompts into fully functional n8n workflows. It empowers users to instantly create AI-powered agents by simply describing what they want in plain English.

---

## 🚀 Overview

AgentForge runs through **three key workflow pipelines**, each powered by a different LLM backend. Depending on the chosen route, it delivers:

- 🔗 A public n8n link  
- 📦 A downloadable `.json` file  
- 📎 Full sticky note instructions and AI Agent Node preconfiguration

---

## 🧠 Architecture

1. **User Input**
   - Prompt entered describing the agent/task.

2. **Template Engine**
   - Reads from a **Google Doc** that holds:
     - Sticky Note JSONs
     - AI Agent Node configuration (tools, memory, output parser)

3. **Model Processor**
   - Chooses model route:
     - `Claude Opus 4` (via OpenRouter)
     - `Mistral 8x7B` (via OpenRouter)

4. **Workflow Generation**
   - Prompt + template is passed to the AI Builder
   - Response goes to:
     - `n8n node` *(if using Claude Opus)*
     - `HTTP node` *(if using OpenRouter directly)*
   - Returns:
     - ✅ A public workflow URL (Opus/Mistral)
     - ✅ OR a downloadable `.json` file (Export route)

---

## 🔁 Workflow Variants

### 1. Claude Opus Builder  
- Uses `claude-3-opus-20240229`  
- Outputs a public URL with importable n8n workflow  
- Best for high-context agents

### 2. Mistral Agent Builder  
- Uses `mistralai/mixtral-8x7b`  
- Modular agent logic  
- Also outputs public link

### 3. JSON Export Agent  
- Outputs a `.json` file  
- Ready for manual import into n8n  
- Includes sticky notes + agent node

---

## 🛠 Tech Stack

- `n8n` — Workflow engine  
- `OpenRouter` — LLM access  
- `Claude Opus & Mistral 8x7B` — Agent generation  
- `Google Docs` — Template storage  
- `HTTP Request Node` — For export/download delivery

---

## 🧰 Setup Instructions

1. Add your `OpenRouter` & `n8n` API keys  
2. Deploy the following workflows:
   - `opus-agent-builder`
   - `mistral-agent-builder`
   - `json-export-agent`
3. Enter your agent prompt  
4. Choose the LLM route  
5. Receive a public link or `.json` file of the workflow

---

## 💡 Use Cases

- Lead gen agents  
- Recursive automation agents (agents that build agents)  
- Task bots and internal tools  
- Prototyping AI workflows in seconds

---

## 📍 Roadmap

- No-code agent composer  
- LangChain & AutoGen integrations  
- Feedback-based auto-improvement  
- Role-based sharing & marketplace

---

## 🤝 Contribute

We welcome prompt engineers, AI agents enthusiasts, and n8n hackers. Fork, build, and shape the future of agent-driven automation.

