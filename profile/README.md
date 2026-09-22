<div align="center">

# Picado Labs

**Deterministic, verify-first infrastructure for autonomous AI software engineering.**

Plan → Route → Execute → Verify → Evaluate

[![GitHub](https://img.shields.io/badge/GitHub-PicadoLabs-181717?style=flat-square&logo=github)](https://github.com/PicadoLabs)
[![Website](https://img.shields.io/badge/Website-picadolabs.me-2e7d58?style=flat-square)](https://picadolabs.me)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

</div>

---

## What it is

Picado Labs builds open-source infrastructure that splits AI-driven software development into deterministic, observable stages instead of one monolithic agent loop:

```
PLAN → ROUTE → EXECUTE → VERIFY → EVALUATE → FEEDBACK
```

## Projects

| Project                                                              | Stage            | What it solves                                                                |
| -------------------------------------------------------------------- | ---------------- | ----------------------------------------------------------------------------- |
| [**build-with-ai**](https://github.com/PicadoLabs/build-with-ai)     | Plan             | Structured AI development workflows with persistent project context           |
| [**AI Model Router**](https://github.com/PicadoLabs/ai-model-router) | Route            | Multi-objective model routing across quality, cost, latency, and capabilities |
| [**Terminal Agent**](https://github.com/PicadoLabs/terminal-agent)   | Execute · Verify | Autonomous coding with sandboxing, recovery, checkpoints, and verification    |
| [**AgentBench**](https://github.com/PicadoLabs/agent-bench)          | Evaluate         | Reproducible evaluation and benchmarking for software-engineering agents      |


## Quickstart

```bash
# Plan
npx build-with-ai init

# Route
python backend/app/cli/main.py route "Build a secure token bucket rate limiter"

# Execute
terminal-agent run "Implement token bucket rate limiter with pytest tests"

# Evaluate
python agentbench.py run --benchmark fix-rate-limiter --provider ollama --model qwen2.5-coder:1.5b
```

See each project's repo for full setup instructions.

## Why

| | Traditional | Picado Labs |
|---|---|---|
| Prompting | Monolithic | Structured workflows |
| Context | Chat history | Persistent memory |
| Model choice | Fixed | Dynamic routing |
| Execution | Direct host access | Sandboxed |
| Verification | AI self-report | Independent testing |
| Evaluation | Subjective | Standardized benchmarks |

## Contributing

Open source under Apache 2.0. PRs welcome — see individual repo issue trackers for good first issues.

```bash
git checkout -b feature/my-feature
pytest && npm test
```

## Community

Built by [Vardhman (Kap10)](https://github.com/Kaap10) — [X](https://x.com/Kap10x) · [LinkedIn](https://www.linkedin.com/company/picado-labs/) · [picadolabs.me](https://picadolabs.me) · picadolabs@gmail.com

---

<div align="center">

**Open source. Practical AI infrastructure. Built to be verified.**

</div>
