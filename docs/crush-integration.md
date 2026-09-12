# Crush integration

Crush is an external Loom client. It is not part of the Loom runtime.

The supported architecture is:

```text
Crush
  -> loom-client-setup
  -> Loom interface / MCP
  -> loom-ai
  -> Workers / Arbiters
  -> model-gateway and other capabilities
```

## Boundary

- `loom-client-setup` owns client-side integration and configuration needed to connect Crush to Loom.
- `loom-setup` owns installation and machine/bootstrap concerns.
- `loom-ai` owns Intent, Worker, Arbiter, execution state, evidence, and task-level orchestration.
- `model-gateway` owns model/provider access and resource selection.
- Capability repositories own their respective contracts and implementations.

The former `crush-demo` repository was a thin Fedora dogfood wrapper around the old `agent-setup`/`agent-ai` architecture. Its useful role is retained here as integration documentation rather than as a separate runtime or demo repository.

## Historical note

The old integration used `agent-setup`, a local FlossWare gateway, and the former agent/worker/arbiter runtime. Those names and boundaries are historical and must not be used for new implementation work.
