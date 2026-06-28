# S.A.N.T.A. x OmegaClaw: The Autonomous Field Researcher

An open-source, localized trust discovery and verification engine built on the SingularityNET / ASI Alliance framework.

---

## 👁️ The Vision: From Chatbots to Field Researchers

Most modern AI agent projects focus on making central LLMs larger and more generalized. **S.A.N.T.A. x OmegaClaw** shifts this paradigm entirely. 

Instead of a generic chatbot, we have built a **Field Researcher**:
1. **S.A.N.T.A.** defines *what* structured, objective trust parameters are needed to verify a local service provider (preventing subjective "review-vibe" bias).
2. **OmegaClaw** acts as the *autonomous boots-on-the-ground agent*, crawling localized sources of truth, resolving technical walls, and compiling structured datasets.
3. This architecture is designed to run locally, preserving processing costs, and can be deployed at scale to form a federated network of learning research nodes.

---

## 🛠️ What We Built (Sprint Outcomes)

We successfully ran a localized production sprint to verify painting contractors within a 25km radius of Lisse/Leiden, Netherlands. 

### 1. The Localized Trust Database (`companies.json`)
A structured database containing verified, cross-referenced parameters for local contractors, including KvK (Chamber of Commerce) registry data, trade association status, and spatial coordinates.

### 2. The Granular Evidence Layer (`/writable/evidence/`)
To enforce zero-guess scoring, the agent generated **12 unique cryptographic-grade JSON evidence files** (one for each business), linking the assigned trust score directly to source stamps, active registration dates, and employee sizes.

### 3. The Objective Trust Vector Model (`METHODOLOGY.md`)
A formalized scoring framework that removes subjective sentiment analysis and rates businesses objectively based on KvK-verification, local directory alignments, and trade certifications.

---

## 📊 Sprint Evaluation (The Honesty Matrix)

In alignment with the Sprint requirements, here is an objective assessment of where our agentic framework stands:

| Capability / Component | Status | Operational Note |
| :--- | :---: | :--- |
| **Internet Research & Crawling** | ✅ | Successfully ran direct Google HTML parsing loops. |
| **Multi-Source Cross-Referencing** | ✅ | Cross-referenced KvK records with regional association data. |
| **Structured Output Generation** | ✅ | Successfully validated and output standardized JSON datasets. |
| **Autonomous Troubleshooting** | ✅ | Wrote inline Python scripts to bypass broken internal search tools. |
| **Long-Term Memory Persistence** | ✅ | ChromaDB successfully maintained location preferences over hours. |
| **Long-Running Workflows** | ⚠️ | High token overhead causes "analysis paralysis" without strict state limits. |
| **File Management & OS Writes** | ⚠️ | Restricted by low-privilege container layers; required root-level execution. |
| **Volume Persistence** | ⚠️ | WSL/Docker sleep cycles sever active API connections, requiring system resets. |

---

## 🧱 The Technical "Walls" We Hit (And How We Engineered Around Them)

Rather than hiding our technical bottlenecks, we present them as engineering insights for the future development of the OmegaClaw ecosystem:

### Wall 1: Low-Privilege Container Writes (`nobody` Permission Block)
* **The Problem:** The container runs as the low-privilege `nobody` user. Writing files to `/PeTTa/` failed silently.
* **The Resolution:** We opened the workspace permissions by executing a root-privileged chmod command (`docker exec -u root`) via WSL, enabling `/writable` paths.

### Wall 2: The Persistent Docker Volume History Loop Trap
* **The Issue:** When the agent fell into a massive 61k-token context loop, restarting the container did nothing because the history was saved on a named Docker volume (`omegaclaw-memory`).
* **The Resolution:** We engineered a hard-reset procedure: explicitly removing both the container and the host volume (`docker volume rm`) to start fresh with a clean 0-token database.

### Wall 3: Tavily API Blindness & Autonomous Python-Scraping Workaround
* **The Issue:** The default `tavily-search` returned no results for Dutch business terms due to a missing API key.
* **The Resolution (Agent Autonomy):** The agent analyzed its container environment, identified that `urllib`, `requests`, and `httpx` were available, and **wrote its own inline Python scripts** to query Google directly with real User-Agent headers, completely bypassing its own broken search tool.

---

## 🗺️ The Architecture & Future Roadmap
code
Code
┌───────────────────────────────────┐
         │         User (Telegram)           │
         └─────────────────┬─────────────────┘
                           │ (auth token)
                           ▼
┌─────────────────────────────────────────────────────┐
│                 OmegaClaw Meta-Layer                │
│  (ChromaDB Vector Memory  |  MeTTa Logic Engine)    │
└──────────────────┬───────────────────────┬──────────┘
                   │                       │
     [Read/Write via Writable Vol]   [Direct Shell Exec]
                   │                       │
                   ▼                       ▼
       📁 /santa/writable/evidence/   📁 Python urllib HTTP scraper
code
Code
1. **Fase 1: State Optimization** - Transition the cognitive loop from "think-and-repeat" to strict incremental writes to prevent context flooding.
2. **Fase 2: Multi-Agent Hierarchy** - Deploy specialized sub-agents: one for crawling directories, one for fetching registry data, and one for computing trust graphs.
3. **Fase 3: MORK Integration** - Store the resulting company network inside a local Hypergraph database to allow complex, multi-hop reasoning.

---

### 📄 License
This prototype is released under the **MIT License**.
