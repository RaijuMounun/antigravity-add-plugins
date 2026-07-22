# Antigravity ADD Plugins 🚀

A curated collection of **Agent-Driven Development (ADD)** architectures designed specifically for **Google Antigravity**. These plugins empower autonomous AI agent teams to plan, write, review, and commit code natively within your local workspaces.

Instead of relying on a single AI assistant, these architectures leverage specialized multi-agent teams (often featuring manager-subordinate hierarchies, local memory persistence, and auto-routing) to handle complex enterprise software development.

## 📂 Repository Structure

Each folder in this repository represents a standalone Antigravity Plugin with its own unique architecture and agent behaviors. 

Please refer to the `README.md` inside each plugin's folder for deep architectural details, workflows, and specific agent roles.

---

## ⚙️ Global Installation

To use any architecture from this repository in your Antigravity environment, you need to place the specific plugin folder inside Antigravity's global configuration directory.

1. **Clone the repository:**
   ```bash
   git clone https://github.com/raijumounun/antigravity-add-plugins.git
   cd antigravity-add-plugins
   ```

2. **Install a Plugin:**
   Copy or symlink the desired architecture folder (e.g., `ue5-fantastic-five`) into your local Antigravity plugins directory.

   **Windows (Copy Method):**
   ```powershell
   Copy-Item -Path ".\<plugin-name>" -Destination "C:\Users\Eren\.gemini\config\plugins\<plugin-name>" -Recurse
   ```
   
   **Windows (Symlink / Junction Method - Recommended):**
   *Using a junction allows you to edit the agents in your cloned repo and have the changes instantly reflect in Antigravity without copying.*
   ```cmd
   mklink /J "C:\Users\Eren\.gemini\config\plugins\<plugin-name>" "C:\path\to\your\repo\<plugin-name>"
   ```

3. **Reload Antigravity:**
   Open a new conversation or restart Antigravity. The new subagents and routing rules will be automatically registered and ready for invocation.

---
*Built for the future of autonomous software development.*
