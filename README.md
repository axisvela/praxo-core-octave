# PRAXO-CORE for GNU Octave

PRAXO-CORE (also written praxocore) is an embeddable, MIT-licensed agent framework. Native Octave Core for the PRAXO-CORE agent framework. This is the independent Octave package root and source tag `octave/v0.9.0`; it shares the implementation in `language/matlab-octave-core/+praxo` with the MATLAB package. It passes all eleven shared vector groups under GNU Octave 11.3.0 and includes the native agent loop, memory store, checkpoint allowlist, lexical path policy, context compaction, event sinks, middleware helpers, tool selection, an OpenTelemetry transport-seam sink, a retriever seam, and synchronous subagent delegation. It does not delegate behavior to Go or another language Core.

## At a glance

| Field | Value |
| --- | --- |
| Package | `praxo-core` |
| Registry | [Octave Packages](https://gnu-octave.github.io/packages/praxo-core/) |
| Install | `pkg install -forge praxo-core` |
| Source version | `0.9.0` |
| Published version | `0.9.0` |
| Publication status | published; indexed 2026-11-26; consumer install smoke not recorded |
| Canonical source tag | [`octave/v0.9.0`](https://github.com/axisvela/praxo-core/tree/octave/v0.9.0) |
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
| OpenAI-compatible model | native | Shared `praxo.openai_compatible` implementation; SSE streaming reassembly |
| Anthropic model | native | Shared `praxo.anthropic_compatible`; `onDelta` reassembles Anthropic SSE |
| Gemini model | native | Shared `praxo.gemini_compatible`; `onDelta` reassembles Gemini SSE |
| MCP client | native (transport seam) | Shared `praxo.mcp_client` implementation |
| Harmovela sink | native | Shared `praxo.harmovela_sink` |
| OpenTelemetry sink | native (transport seam) | Shared `praxo.otel_sink`; caller supplies OTLP/HTTP transport |
| Subagent delegation | native (synchronous seam) | Shared `praxo.subagent_run`; no asynchronous manager |
| Retriever | native | Shared `praxo.document` and `praxo.retrieve_documents` |

## Examples

Runnable examples live under [`language/octave/examples`](language/octave/examples).

| Example | What it shows |
| --- | --- |
| [advanced-delegation](language/octave/examples/advanced-delegation) | Octave wrappers for the shared MATLAB/Octave delegation and governance examples. |
| [consumer](language/octave/examples/consumer) | Octave reuses the shared MATLAB/Octave example at `language/matlab/examples/consumer/consumer_example.m`. The `run.m` wrapper adds the shared Core and example paths, then runs the same deterministic allow/deny check. |
| [live-model](language/octave/examples/live-model) | Octave reuses the shared MATLAB/Octave example at `language/matlab/examples/live-model/live_model_example.m`. The `run.m` wrapper adds the shared Core and example paths, then runs the same OpenAI-compatible `get_time` flow. |
| [representative-chain](language/octave/examples/representative-chain) | Octave wrapper for the shared MATLAB/Octave representative chain. |

## Scenario Tutorials

Scenario-oriented tutorials live under `language/octave/Tutorial`. Planning context: [Tutorial Plan](https://axisvela.github.io/praxo-core/getting-started/tutorial-plan/), [100 candidate agent scenarios](https://axisvela.github.io/praxo-core/getting-started/agent-scenarios/), and [Tutorial Catalog](https://axisvela.github.io/praxo-core/getting-started/tutorial-catalog/).

| Path | What it shows |
| --- | --- |
| [Tutorial](language/octave/Tutorial) | Application tutorials live in `Tutorial/`, alongside focused `language/go/examples/`. |
| [signal-trends](language/octave/Tutorial/signal-trends) |  |
| [vibration-review](language/octave/Tutorial/vibration-review) | A bounded vibration-analysis tutorial. It computes FFT/RMS for normal and anomalous signals, derives a high-frequency energy ratio, and lets Core choose normal or inspection review. No device is accessed and no failure is predicted. |
| [water-quality](language/octave/Tutorial/water-quality) | A bounded pond water-quality tutorial. It computes fixed dissolved-oxygen and temperature indicators, compares oxygen with a threshold, and lets Core choose a normal or aeration-review branch. No sensor or aerator is accessed. |

## Reference Applications

No accepted end-to-end reference application is recorded for this language yet. Candidate goals are tracked in the [Reference Application Portfolio](https://axisvela.github.io/praxo-core/project/planning/roadmap/#reference-application-portfolio).

## Verify

This mirror contains the language source and the shared `spec/` vectors, so the implementation can be built and tested here. See [`language/octave/README.md`](language/octave/README.md) for the exact commands. The monorepo CI runs conformance, API snapshot, and native tests for this implementation.

## Boundaries

Reference application source is not end-to-end portfolio acceptance; follow each README's scope and evidence.
PRAXO-CORE is not a hosted model, workflow engine, identity provider, or safety controller. Do not infer exactly-once execution, complete sandbox isolation, production security certification, live-provider behavior, or physical safety from this package.

## Community

- X: <https://x.com/axisvela>
- Weibo: <https://weibo.com/u/1936025761>
- LinkedIn: <https://www.linkedin.com/company/axisvela/>
- Facebook: <https://www.facebook.com/profile.php?id=61596905732406>
- YouTube: <https://www.youtube.com/@axisvela>
- Discord: <https://discord.com/channels/1575163993767809064/1575164343148875977>
- GitHub Discussions: <https://github.com/axisvela/praxo-core/discussions>
- GitHub Issues: <https://github.com/axisvela/praxo-core/issues>
- Documentation: <https://axisvela.github.io/praxo-core/>
- Architect: <https://axisvela.architect.pub>

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

This repository is a discovery mirror of the canonical GNU Octave source. The monorepo remains the source of truth and the release workflow source. The mirror's `main` branch tracks current source, not a release snapshot. Source tags refer to the canonical monorepo and are not necessarily present in this mirror; syncing the branch does not publish mirror tags or registry packages.


MIT licensed.
