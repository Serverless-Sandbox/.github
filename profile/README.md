<div align="center">

**Cloud sandboxes for AI agents — built on Alibaba Cloud Function Compute.**

</div>

---

Serverless Sandbox is an open-source Python SDK and CLI for creating, managing, and interacting with secure cloud sandboxes designed for AI agents. Powered by Alibaba Cloud Function Compute, it gives every agent its own isolated Linux environment with filesystem, networking, and terminal access — spun up in seconds, torn down on demand. If you've used E2B, you'll feel right at home: our API is protocol-compatible, so migration is a one-line change.

- **E2B Protocol Compatible** — Drop-in replacement for E2B's data-plane API. Migrate existing projects with minimal changes.
- **AI-First Design** — Sandboxes ship with pre-installed AI CLI tools and an MCP Server, making them first-class citizens in agent workflows. Zero LLM dependency in the SDK itself.
- **Zero Config** — Set `SANDBOX_API_KEY` and go. Sensible defaults mean you write three lines of Python, not thirty.
- **`@sandbox` Decorator** — Modal-style declarative API. Decorate any function to run it remotely in a cloud sandbox.
- **SandboxPool** — Pre-warmed sandbox pools for high-concurrency workloads. Acquire, execute, release — no cold starts.
- **Alibaba Cloud Native** — Deep integrations with VPC, OSS, NAS, SLS, and custom domain binding for enterprise-grade deployments.
- **Powerful CLI (`sbox`)** — Create, list, exec, kill, deploy templates, manage secrets — all from your terminal.
- **Six-Layer Architecture** — From transport to AI integration, each layer has a single responsibility. Plug in at any level you need.

## 📦 Repositories

| Repository | Description |
|:--|:--|
| [`serverless-sandbox`](https://github.com/serverless-sandbox/serverless-sandbox) | Core SDK & CLI — sandbox lifecycle, file I/O, code execution, agent tools, and more. |
| [`awesome-templates`](https://github.com/serverless-sandbox/awesome-templates) | Community-curated sandbox templates — Python, Node.js, data science, code interpreters. |

## 🚀 Quick Start

```bash
pip install serverless-sandbox
```

```python
from serverless_sandbox import Sandbox

async with await Sandbox.create(template="python-base") as sb:
    result = await sb.run_code("print('Hello from the cloud!')")
    print(result.text)  # Hello from the cloud!
```

> Need the CLI? `pip install "serverless-sandbox[cli]"` — then run `sbox create --template python-base`.
