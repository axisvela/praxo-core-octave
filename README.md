# PRAXO-CORE for GNU Octave

Native Octave Core for the PRAXO-CORE agent framework. This is the independent Octave package root and source tag `octave/v0.5.0`; it shares the implementation in `language/matlab-octave-core/+praxo` with the MATLAB package. It passes all eleven shared vector groups under GNU Octave 11.3.0 and includes the native agent loop, memory store, checkpoint allowlist, lexical path policy, context compaction, event sinks, middleware helpers, tool selection, an OpenTelemetry transport-seam sink, a retriever seam, and synchronous subagent delegation. It does not delegate behavior to Go or another language Core.

## At a glance

| Field | Value |
| --- | --- |
| Package | `praxo-core` |
| Registry | [Octave Packages](https://github.com/axisvela/praxo-core/releases/download/octave/v0.2.1/praxo-core-0.2.1.tar.gz) |
| Install | `pkg install -forge praxo-core` |
| Source version | `0.5.0` |
| Published version | `0.2.1` |
| Source tag | `octave/v0.5.0` |
| Tier | Core |
| Contract | `SPEC_VERSION` `0.2.0` |
| Documentation | https://axisvela.github.io/praxo-core/languages/octave/ |
| License | MIT |

## Highlights

- OpenAI-compatible model: native
- Anthropic model: native
- Gemini model: native
- MCP client: native (transport seam)
- Harmovela sink: native
- OpenTelemetry sink: native (transport seam)
- Subagent delegation: native (synchronous seam)
- Retriever: native

## Quick start

Install the published package:

```bash
pkg install -forge praxo-core
```

```bash
python language/octave/run-tests.py
python language/octave/api-snapshot.py --check
```

See the [full GNU Octave README](language/octave/README.md) for complete installation, build, and verification commands.

## What's included

| Capability | Status | Detail |
| --- | --- | --- |
| OpenAI-compatible model | native | Shared `praxo.openai_compatible` implementation |
| Anthropic model | native | Shared `praxo.anthropic_compatible` |
| Gemini model | native | Shared `praxo.gemini_compatible` |
| MCP client | native (transport seam) | Shared `praxo.mcp_client` implementation |
| Harmovela sink | native | Shared `praxo.harmovela_sink` |
| OpenTelemetry sink | native (transport seam) | Shared `praxo.otel_sink`; caller supplies OTLP/HTTP transport |
| Subagent delegation | native (synchronous seam) | Shared `praxo.subagent_run`; no asynchronous manager |
| Retriever | native | Shared `praxo.document` and `praxo.retrieve_documents` |

## Examples

See the canonical examples: https://github.com/axisvela/praxo-core/tree/main/language/matlab/examples.

## Verify

This mirror contains the language source and the shared `spec/` vectors, so the implementation can be built and tested here. See [`language/octave/README.md`](language/octave/README.md) for the exact commands. The monorepo CI runs conformance, API snapshot, and native tests for this implementation.

## Community

- X: <https://x.com/axisvela>
- Weibo: <https://weibo.com/u/1936025761>

## Repository layout

- `language/octave/` — implementation source, tests, API snapshot, and examples
- `spec/` — shared contract, vectors, and parity inventories
- `LICENSE` — MIT license

## Canonical source

- Canonical source: https://github.com/axisvela/praxo-core/tree/main/language/octave
- Registry introduction: `language/octave/REGISTRY.md`
- Machine-readable entry: `language/octave/llms.txt` and `language/octave/llms.md`
- Mirror repository: https://github.com/axisvela/praxo-core-octave
- Release index: https://axisvela.github.io/praxo-core/languages/registry-status/

This repository is a discovery mirror of the canonical GNU Octave source. The monorepo remains the source of truth and the release workflow source.

PRAXO-CORE is not a hosted model, workflow engine, identity provider, or safety controller. Do not infer exactly-once execution, complete sandbox isolation, production security certification, live-provider behavior, or physical safety from this package.

MIT licensed.
