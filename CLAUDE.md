# CLAUDE.md

Python-based MCP server for macOS Calendar. Uses pyobjc to talk to EventKit directly (no AppleScript), providing calendar CRUD operations.

## Stack

- Python >=3.12, hatchling build system
- `mcp[cli]`, `pyobjc`, `loguru`
- pytest for tests, ruff for linting (line-length 120)

## Build & Test

```sh
uv sync              # install deps
uv run mcp-ical      # run the server
uv run pytest        # run tests
uv run ruff check .  # lint
uv run ruff format . # format
```

## Layout

- Source lives under `src/mcp_ical/`; entry point is `server.py`
- Tests in `tests/`
- Unlike the other MCP servers in this org, this one uses pyobjc native bindings rather than AppleScript
