# A2A Python Mock Generator

This directory contains runnable examples demonstrating how to build and interact with an A2A-compliant agent using the Python SDK.

```bash
docker build . -t mock-generator:latest
```


```bash
docker run -p 41241:41241 -p 41242:41242 mock-generator:latest
```

# FIXME
## Contents

| File | Role | Description |
|---|---|---|
| `hello_world_agent.py` | **Server** | A2A agent server |
| `cli.py` | **Client** | Interactive terminal client |

The samples are designed to work together out of the box: the agent listens on `http://127.0.0.1:41241`, which is the default URL used by the client.
---

## `hello_world_agent.py` — Agent Server

Implements an A2A agent that responds to simple greeting messages (e.g., "hello", "how are you", "bye") with text replies, simulating a 1-second processing delay.

Demonstrates:
- Subclassing `AgentExecutor` and implementing `execute()` / `cancel()`
- Publishing streaming status updates and artifacts via `TaskUpdater`
- Exposing all three transports in both protocol versions (v1.0 and v0.3 compat) simultaneously:
  - **JSON-RPC** (v1.0 and v0.3) at `http://127.0.0.1:41241/a2a/jsonrpc`
  - **HTTP+JSON (REST)** (v1.0 and v0.3) at `http://127.0.0.1:41241/a2a/rest`
  - **gRPC v1.0** on port `50051`
  - **gRPC v0.3 (compat)** on port `50052`
- Serving the agent card at `http://127.0.0.1:41241/.well-known/agent-card.json`

**Run:**

```bash
uv run python true_agent_50001.py
```

