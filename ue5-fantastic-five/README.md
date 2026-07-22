# UE5 Fantastic Five 🎮

The **Fantastic Five** is a highly specialized, enterprise-grade Agent-Driven Development (ADD) architecture tailored for **Unreal Engine 5 C++** development. 

This architecture moves beyond treating LLMs as mere "code writers." Instead, it implements a **Manager-Subordinate paradigm**, where agents act as Lead Developers and QA Managers who dynamically spawn their own subagents, enforce a strict *Design-First* workflow, and utilize a highly disciplined local JSON-based memory system known as the Memory Bank Protocol.

## 🧠 The Architecture (The 5 Agents)

### 1. 🎼 Orchestrator (The Mastermind)
- **Role:** Project Manager & Workflow Router.
- **Workflow:** When a task is requested, the Orchestrator **never** writes code immediately. It first initiates a **Design Phase** with the user, querying the Archivist for existing project constraints. Once the user approves the design roadmap, it delegates the execution to the Lead Developer. 
- **Memory Protocol:** It operates strictly under the "Read First" rule (pulling context before acting) and the mandatory "Write Last" rule (ordering the Archivist to update the state once a task is completed).

### 2. 📚 Archivist (The Memory Bank / Local RAG)
- **Role:** Local Knowledge & Dependency Manager.
- **Workflow:** Maintains the **4 Core JSON Pillars** in a hidden `.antigravity/memory/` directory within your project. It acts as a highly efficient, zero-token-bloat RAG system.
  - `SystemPatterns.json`: Core architectural rules and restricted libraries.
  - `ProjectMap.json`: Module dependencies and folder context.
  - `ActiveState.json`: The team's current focus and open bugs.
  - `Progress.json`: Completed features and long-term roadmap.

### 3. 👨‍💻 Lead Coder (The Lead Developer)
- **Role:** C++ Architect & Team Lead.
- **Workflow:** Receives the approved design from the Orchestrator. It does not blindly write a massive `.cpp` file in one breath. Equipped with `subagent_tools`, it can spawn its own temporary subagents (e.g., `HeaderArchitect`, `CppImplementer`, `RefactorSpecialist`) to handle complex UE5 macros, `TObjectPtr` memory safety, and Event-Driven decoupling.

### 4. 🕵️‍♂️ Senior Reviewer (The QA Manager)
- **Role:** The Gatekeeper of Quality & Performance.
- **Workflow:** The most critical agent in the pipeline. Upon receiving code from the Lead Developer, it dynamically spawns **3 specialized auditors**:
  1. **Performance & Security Auditor:** Inspects Big O complexity, Tick() abuse, GC optimization, and cache coherency.
  2. **Architecture & SOLID Validator:** Ensures adherence to GoF patterns, strict SOLID principles, and backward compatibility.
  3. **UE5 Standards Enforcer:** Verifies Epic Games' C++ standards, macro flags, Subsystem usage, and replication rules.
  
  If any auditor raises a red flag, the QA Manager aggregates a "Redjection Report" and kicks the code back to the Lead Developer. Once flawlessly approved, it runs the native Unreal Build Tool (UBT) to guarantee compilation.

### 5. 🐙 Git Agent (The Version Control Expert)
- **Role:** Repository Maintainer.
- **Workflow:** Steps in only after the QA Manager has approved and successfully compiled the code. It analyzes the diffs semantically and executes clean, atomic, conventional commits (feat, fix, refactor) directly on your local machine.

## 🚀 Key Features

*   **Memory Bank Protocol:** Agents strictly follow "Read First" and "Write Last" operations. The system NEVER forgets the state of the project or leaves a task unrecorded in the `ActiveState.json` or `Progress.json`.
*   **Zero Assumptions:** A system-wide guardrail built into every agent. If an agent does not understand a diff, a class, or a constraint, guessing is strictly forbidden. They will actively query the Archivist or halt and ask the user.
*   **Design-First Philosophy:** Zero code is written until a comprehensive architectural consensus is reached between the User, Orchestrator, and Archivist.
*   **Inception (Subagent Nesting):** Lead agents spawn their own specialized sub-agents for granular tasks, eliminating the classic "LLM Context Blindspot" on second-pass reviews.
*   **Token-Efficient RAG:** Completely replaces expensive global context windows with targeted `grep` operations over local JSON structured memory.
*   **Auto-Routing:** When installed globally, any coding request inside your UE5 workspace automatically triggers the Orchestrator silently in the background.

---
*Elevate your Unreal Engine development with a dedicated AI studio.*
