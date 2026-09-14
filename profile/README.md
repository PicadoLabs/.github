<div align="center">

# Picado Labs

**Deterministic, verify-first infrastructure for autonomous AI software engineering.**

Plan → Route → Execute → Verify → Evaluate

[![GitHub](https://img.shields.io/badge/GitHub-PicadoLabs-181717?style=flat-square&logo=github)](https://github.com/PicadoLabs)
[![Website](https://img.shields.io/badge/Website-picadolabs.me-2e7d58?style=flat-square)](https://picadolabs.me)
[![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)](https://opensource.org/licenses/MIT)

</div>

---

## Table of Contents

- [Overview](#overview)
- [Ecosystem](#ecosystem)
- [Core Projects](#core-projects)
  - [build-with-ai](#01-build-with-ai)
  - [Model Router](#02-model-router)
  - [Terminal Agent](#03-terminal-agent)
  - [AgentBench](#04-agentbench)
- [Closed-Loop Architecture](#closed-loop-architecture)
- [Why Picado Labs](#why-picado-labs)
- [Quickstart](#quickstart)
- [Contributing](#contributing)
- [Repositories](#repositories)
- [Community](#community)

---

## Overview

Picado Labs builds open-source infrastructure for autonomous AI software development.

The ecosystem separates AI-driven development into deterministic stages:

```text
PLAN
  ↓
ROUTE
  ↓
EXECUTE
  ↓
VERIFY
  ↓
EVALUATE
  ↓
FEEDBACK
```

The goal is simple: make AI software engineering **more reliable, observable, secure, and measurable**.

---

## Ecosystem

| Stage         | Project                  | Purpose                                                        |
| ------------- | ------------------------ | ---------------------------------------------------------------|
| 01 • Plan     | **build-with-ai**        | Prompt architecture, context and project workflow              |
| 02 • Route    | **Model Router**         | Intelligent model selection based on quality, cost and latency |
| 03 • Execute  | **Terminal Agent**       | Autonomous coding inside controlled sandboxes                  |
| 04 • Verify   | **Independent Verifier** | Objective test-based completion verification                   |
| 05 • Evaluate | **AgentBench**           | Benchmark and measure coding-agent performance                 |

---

# Core Projects

## 01. build-with-ai

**Plan & Orchestrate — Zero-API Prompt Architect**

GitHub: [PicadoLabs/build-with-ai](https://github.com/PicadoLabs/build-with-ai)
npm: [build-with-ai](https://www.npmjs.com/package/build-with-ai)

An interactive CLI that turns software goals into structured engineering phases and context-aware prompts.

### Key Features

* Zero API keys or external telemetry
* Persistent project context in `.buildwithai/`
* Dynamic decision injection into future prompts
* 7 production workflow templates
* Deterministic documentation export

### Quickstart

```bash
npx build-with-ai init
npx build-with-ai next
npx build-with-ai done
npx build-with-ai context
npx build-with-ai export
```

---

## 02. Model Router

**Route & Optimize — AI Traffic Control**

GitHub: [PicadoLabs/ai-model-router](https://github.com/PicadoLabs/ai-model-router)

An explainable routing gateway that selects the most suitable local or cloud model for each request.

### Key Features

* Sub-3ms routing overhead
* Pareto optimization across quality, cost and latency
* Capability and context-window filtering
* Provider fallback handling
* Budget control and telemetry
* FastAPI + React Control Room

### Quickstart

```bash
git clone https://github.com/PicadoLabs/ai-model-router.git
cd ai-model-router
pip install -r requirements.txt

python backend/app/cli/main.py doctor
python backend/app/cli/main.py route "Build an async rate limiter in Python"
python backend/app/cli/main.py run "Debug distributed async deadlock"
```

---

## 03. Terminal Agent

**Execute & Verify — Sandboxed Coding Agent**

GitHub: [PicadoLabs/terminal-agent](https://github.com/PicadoLabs/terminal-agent)

A verify-first autonomous coding agent that executes engineering tasks inside controlled environments and requires objective verification before completion.

### Key Features

* Independent test verification
* Process-tree sandboxing with `psutil` and Docker
* Deterministic repository context ranking
* 5-tier command security policy
* Secret detection and redaction
* 12-category failure recovery
* SQLite checkpoints and rollback

### Quickstart

```bash
pip install terminal-agent

terminal-agent run "Implement JWT authentication with tests"
terminal-agent status
terminal-agent diff
terminal-agent doctor
terminal-agent rollback <checkpoint-id>
```

---

## 04. AgentBench

**Benchmark & Evaluate — Coding Agent Evaluation**

GitHub: [PicadoLabs/agent-bench](https://github.com/PicadoLabs/agent-bench)

A provider-agnostic benchmark platform for evaluating autonomous coding agents on realistic software-engineering tasks.

### Key Features

* 12 standardized Python and Node.js tasks
* Local and Docker execution
* Multiple agent architectures
* Automated failure classification
* 5D composite SWE scoring
* GitHub PR ingestion
* Web dashboard and CI integration

### Scoring

```text
Score =
0.50 × Correctness
+ 0.25 × Pass Rate
+ 0.10 × Code Quality
+ 0.10 × Efficiency
+ 0.05 × Repair
```

### Quickstart

```bash
git clone https://github.com/PicadoLabs/agent-bench.git
cd agent-bench

pip install -r requirements.txt
pip install -e .

python agentbench.py doctor
python agentbench.py init
python agentbench.py list
python agentbench.py run \
  --benchmark fix-rate-limiter \
  --provider ollama \
  --model qwen2.5-coder:1.5b
```

---

# Closed-Loop Architecture

```text
┌───────────────┐
│     PLAN      │
│ build-with-ai │
└───────┬───────┘
        ↓
┌───────────────┐
│     ROUTE     │
│  Model Router │
└───────┬───────┘
        ↓
┌───────────────┐
│    EXECUTE    │
│ Terminal Agent│
└───────┬───────┘
        ↓
┌───────────────┐
│     VERIFY    │
│    Verifier   │
└───────┬───────┘
        ↓
┌───────────────┐
│    EVALUATE   │
│   AgentBench  │
└───────┬───────┘
        ↓
   TELEMETRY
        │
        └──────→ Router / Agent
```

---

# Why Picado Labs

| Area         | Traditional Approach | Picado Labs                     |
| ------------ | --------------------- | -------------------------------- |
| Prompting    | Monolithic prompts    | Structured workflows             |
| Context      | Chat history          | Persistent deterministic memory  |
| Model Choice | Fixed model           | Dynamic routing                  |
| Execution    | Direct host access    | Sandboxed execution              |
| Verification | AI self-report        | Independent testing              |
| Recovery     | Retry blindly         | Classified repair + rollback     |
| Evaluation   | Subjective            | Standardized benchmarks          |

---

# Quickstart

Run the complete workflow:

```bash
# 1. Plan
npx build-with-ai init

# 2. Check infrastructure
python backend/app/cli/main.py doctor
terminal-agent doctor
python agentbench.py doctor

# 3. Route
python backend/app/cli/main.py route \
  "Build a secure token bucket rate limiter in Python"

# 4. Execute
terminal-agent run \
  "Implement token bucket rate limiter with pytest tests"

# 5. Evaluate
python agentbench.py run \
  --benchmark fix-rate-limiter \
  --provider ollama \
  --model qwen2.5-coder:1.5b
```

---

# Contributing

Picado Labs is open source under the **MIT License**.

Contributions are welcome across:

* New build-with-ai templates
* Model provider adapters
* Sandbox runtimes
* Failure classifiers
* Benchmark tasks
* Evaluation metrics

### Development

```bash
git checkout -b feature/my-feature
git commit -m "feat(router): add new routing heuristic"
pytest
npm test
```

Then open a Pull Request.

---

# Repositories

| Project        | Repository                                               | Issues                                                              |
| -------------- | --------------------------------------------------------- | -------------------------------------------------------------------- |
| build-with-ai  | [GitHub](https://github.com/PicadoLabs/build-with-ai)    | [Issues](https://github.com/PicadoLabs/build-with-ai/issues)        |
| Model Router   | [GitHub](https://github.com/PicadoLabs/ai-model-router)  | [Issues](https://github.com/PicadoLabs/ai-model-router/issues)      |
| Terminal Agent | [GitHub](https://github.com/PicadoLabs/terminal-agent)   | [Issues](https://github.com/PicadoLabs/terminal-agent/issues)       |
| AgentBench     | [GitHub](https://github.com/PicadoLabs/agent-bench)      | [Issues](https://github.com/PicadoLabs/agent-bench/issues)          |
| Organization   | [PicadoLabs](https://github.com/PicadoLabs)              | [Good first issues](https://github.com/issues/search?q=org%3APicadoLabs+is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22) |

---

# Community

**Founder & Maintainer:** [Vardhman (Kap10)](https://github.com/Kaap10)

* [GitHub](https://github.com/Kaap10)
* [X](https://x.com/Kap10x)
* [Picado Labs X](https://x.com/PicadoLabs)
* [LinkedIn](https://www.linkedin.com/company/picado-labs/)
* [Website](https://picadolabs.me)
* Email: [picadolabs@gmail.com](mailto:picadolabs@gmail.com)

---

<div align="center">

**Picado Labs · Open source. Practical AI infrastructure. Built to be verified.**

</div>
