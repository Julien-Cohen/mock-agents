# A2A Python SDK — Sample Clients

This directory contains runnable examples demonstrating how to build and interact with an A2A-compliant agent using the Python SDK.

## Contents

| File | Role | Description |
|---|---|---|
| `hello_world_agent.py` | **Server** | A2A agent server |
| `cli.py` | **Client** | Interactive terminal client |

The samples are designed to work together out of the box: the agent listens on `http://127.0.0.1:41241`, which is the default URL used by the client.
---



## `cli.py` — Client

An interactive terminal client with full visibility into the streaming event flow. Each `TaskStatusUpdate` and `TaskArtifactUpdate` event is printed as it arrives.

Features:
- Transport selection via `--transport` flag (`JSONRPC`, `HTTP+JSON`, `GRPC`)
- Session management (`context_id` persisted across messages, `task_id` per task)
- Graceful error handling for HTTP and gRPC failures

**Run:**

```bash
# Connect to the local hello_world_agent (default):
uv run python cli_41241.py

# Connect to a different URL, using gRPC:
uv run python cli_41241.py --url http://192.168.1.10:41241 --transport GRPC
```

Then type a message like `hello` and press Enter.

Type `/quit` or `/exit` to stop, or press `Ctrl+C`.
