# Antigravity ADD Plugins 🚀

A curated collection of **Agent-Driven Development (ADD)** architectures designed specifically for Google Antigravity. These plugins empower autonomous AI agent teams to plan, write, review, and commit code natively within your projects.

## 🏗️ Available Architectures

### `ue5-fantastic-five`
A specialized 5-agent team tailored for **Unreal Engine 5 C++** development.
- **Orchestrator**: The mastermind. Breaks down tasks, manages states, and distributes context.
- **Lead Coder**: The C++ Architect. Writes highly optimized, memory-safe UE5 C++ code using appropriate macros and memory management.
- **Senior Reviewer**: The Gatekeeper. Ruthlessly reviews code, simulates static analysis, and ensures perfection before code touches the disk.
- **Archivist**: The Memory Bank. Manages project dependencies and the JSON-based memory/RAG system to prevent hallucinations.
- **Git Agent**: The Version Control Expert. Analyzes diffs and creates atomic, conventional commits automatically.

---

## ⚙️ Installation

To use any of these architectures in your Antigravity environment, you need to place the plugin folder inside Antigravity's global configuration directory.

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/antigravity-add-plugins.git
   cd antigravity-add-plugins
   ```

2. **Install the Plugin:**
   Copy or symlink the desired architecture folder (e.g., `ue5-fantastic-five`) into your local Antigravity plugins directory.

   **Windows (Copy Method):**
   ```powershell
   Copy-Item -Path ".\ue5-fantastic-five" -Destination "C:\Users\Eren\.gemini\config\plugins\ue5-fantastic-five" -Recurse
   ```
   
   **Windows (Symlink / Junction Method - Recommended):**
   *Using a junction allows you to edit the agents in your repo and have the changes instantly reflect in Antigravity without copying.*
   ```cmd
   mklink /J "C:\Users\Eren\.gemini\config\plugins\ue5-fantastic-five" "C:\Users\Eren\Desktop\-\Projeler\antigravity-add-plugins\ue5-fantastic-five"
   ```

3. **Reload Antigravity:**
   Open a new conversation in Antigravity. The new subagents will be automatically registered and ready for invocation.

---

## 🚀 How to Use

Once installed, the agents will be natively available in your Antigravity desktop application.

1. Open your project workspace (e.g., your Unreal Engine 5 project directory) in Antigravity.
2. In the chat, simply invoke the Orchestrator to begin a task. For example:
   > *"Invoke the Orchestrator agent to create a new Health Component that prints a message when damage is taken."*
3. The Orchestrator will take over, query the Archivist for context, command the Lead Coder to write the file, pass it to the Senior Reviewer for validation (and native UBT execution), and finally hand it off to the Git Agent for a clean commit.

---

## 🧠 The "Local Memory" Concept (JSON RAG)
These architectures utilize a high-performance, token-efficient local memory system. Instead of relying on expensive global context windows or external vector databases, the **Archivist** agent maintains structured `.json` files in a hidden `.antigravity/memory/` directory within your project. 

This allows the agents to instantly `grep` project architecture, dependencies, and rules with zero token bloat and absolute precision.

---
*Built for the future of autonomous software development.*
