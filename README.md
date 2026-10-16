# 🤖 AutoGen Multi-Agent Simulator



---

## 📌 About

This is an interactive, browser-based simulator that visually demonstrates how **Microsoft's AutoGen** framework orchestrates multiple LLM-powered agents to solve a task through conversation.

Instead of just reading about how AutoGen works, you can **watch it happen** — pick a task, run the simulation, and see agents like the Planner, Coder, and Critic pass messages back and forth in real time, with benchmark relevance highlighted at each step.

---

## 🚀 Live Demo

Open `autogen-simulator.html` directly in any browser — no server, no install, no dependencies.

```bash
# Just open the file
open autogen-simulator.html        # macOS
start autogen-simulator.html       # Windows
xdg-open autogen-simulator.html    # Linux
```

Or host it instantly with GitHub Pages (see [Deployment](#-deployment) below).

---

## 🎯 Features

### Simulator Tab
- Choose from **4 real coding tasks** to simulate:
  - 🔢 **Merge sort** — write and verify a Python sort algorithm
  - 🌐 **REST API bug** — fix a broken FastAPI authentication endpoint
  - 🧠 **ML pipeline** — build a scikit-learn training pipeline
  - 🗄️ **SQL optimisation** — speed up a slow aggregation query
- Watch **5 agents** collaborate in sequence with live activity indicators
- Each agent message shows the relevant **benchmark tag** — explaining *why* that capability matters at that exact turn

### Benchmarks Tab
A concise reference card for all five benchmarks covered in the report, each with an AutoGen-specific relevance note and a representative score bar:

| Benchmark | What it measures | AutoGen role |
|-----------|-----------------|--------------|
| MMLU | Broad world knowledge (57 subjects) | Planner agent |
| GPQA | Graduate-level expert reasoning | Final synthesis agent |
| HumanEval | Python code correctness (pass@1) | Coder agent |
| SWE-bench Verified | Real GitHub issue resolution | Full coding sessions |
| TruthfulQA | Resistance to hallucination | Critic agent |

### Architecture Tab
Each AutoGen component explained in plain terms — UserProxyAgent, GroupChatManager, Planner, Coder, Critic — with the benchmark that best predicts each agent's real-world reliability.

---

## 🏗️ AutoGen Agent Roles (simulated)

```
UserProxy  ──►  GroupChatManager  ──►  Planner
                                          │
                                          ▼
                                        Coder  ◄──► Code Executor
                                          │
                                          ▼
                                        Critic
                                          │
                                          ▼
                                    UserProxy (TERMINATE)
```

| Agent | Color | Key benchmark |
|-------|-------|---------------|
| UserProxy | 🔵 Blue | — (task initiator / executor) |
| GroupChatManager | 🩵 Teal | — (conversation orchestrator) |
| Planner | 🟣 Purple | MMLU · GPQA |
| Coder | 🟢 Green | HumanEval · SWE-bench Verified |
| Critic | 🟠 Amber | TruthfulQA |

---

## 📁 Repository Structure

```
autogen-simulator/
│
├── autogen-simulator.html   # Main project file (entire app in one file)
└── README.md                # This file
```

The entire app — HTML, CSS, and JavaScript — lives in a single self-contained file. No frameworks, no build step, no package.json.

---

## 🌐 Deployment

### GitHub Pages (recommended)
1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)`
4. Your simulator will be live at:
   ```
   https://<your-username>.github.io/<repo-name>/autogen-simulator.html
   ```


---

## 🛠️ Tech Stack

| Layer | Choice | Reason |
|-------|--------|--------|
| Structure | Vanilla HTML5 | Zero dependencies, works offline |
| Styling | CSS custom properties + dark theme | No framework needed |
| Logic | Vanilla JavaScript | Lightweight, no build step |
| Fonts | Inter + JetBrains Mono (Google Fonts) | Clean UI + code readability |

---

## 📚 References

- Microsoft. *AutoGen Documentation — Agents, Conversations, and Group Chat*, 2025–2026.
- Hendrycks, D. et al. *Measuring Massive Multitask Language Understanding (MMLU)*, 2021.
- Rein, D. et al. *GPQA: A Graduate-Level Google-Proof Q&A Benchmark*, 2023.
- Chen, M. et al. *Evaluating Large Language Models Trained on Code (HumanEval)*, 2021.
- Jimenez, C. et al. *SWE-bench: Can Language Models Resolve Real-World GitHub Issues?*, 2023.

---

## 📄 License

This project is submitted as academic coursework for UNAIL411 at G H Raisoni College of Engineering, Nagpur (Winter 2026).
