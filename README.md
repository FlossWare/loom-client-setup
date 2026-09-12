# loom-client-setup

**Configure external clients to consume Loom.**

This repository owns client-side integration setup for the Loom runtime. It does not install or implement Loom itself.

## Supported client boundary

```text
Crush
Claude Code
Codex
Cursor
   │
   ▼
loom-client-setup
   │
   ├── endpoint configuration
   ├── MCP/API configuration
   ├── authentication
   ├── diagnostics
   └── client-specific integration
             │
             ▼
          loom-ai
```

The first implementation target is Crush, followed by generalized configuration for other compatible clients.

## Responsibility split

- `loom-ai` owns execution, Intent, Workers, Arbiters, evidence, evaluation, and runtime contracts.
- `loom-setup` installs/configures the Loom runtime and its infrastructure/model-gateway environment.
- `loom-client-setup` configures external clients to consume an already configured Loom instance.
- `model-gateway` owns provider/model/resource invocation and selection.

Client setup must not duplicate Loom runtime configuration or provider credentials.

## Status

The repository is intentionally minimal while the Loom runtime contracts stabilize. New client integration work should consume Loom through its public MCP/API boundary rather than reaching into Loom internals.

## License

MIT
