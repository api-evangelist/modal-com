# Modal (modal-com)

Modal is a serverless cloud platform for AI and data workloads. Developers write ordinary Python and run it on remote GPUs and CPUs with sub-second cold starts, instant autoscaling, and declarative container images. Modal's primitives — Functions, Sandboxes, Volumes, Images, Secrets, Dicts, Queues, Schedules, and Web Endpoints — cover inference, fine-tuning, multi-node training, batch processing, agent code execution, and HTTP/web APIs.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/modal-com/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

 - Serverless, GPU, Cloud Compute, AI Infrastructure, Sandboxes, Inference, Training, Batch Processing, Python, TypeScript, Go

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## GPU Pricing

Per-second on-demand rates for Modal Functions:

| GPU | Memory | $/second |
|---|---|---|
| NVIDIA T4 | 16 GB | $0.000164 |
| NVIDIA L4 | 24 GB | $0.000222 |
| NVIDIA A10 | 24 GB | $0.000306 |
| NVIDIA L40S | 48 GB | $0.000542 |
| NVIDIA A100 40GB | 40 GB | $0.000583 |
| NVIDIA A100 80GB | 80 GB | $0.000694 |
| NVIDIA RTX PRO 6000 | 96 GB | $0.000842 |
| NVIDIA H100 | 80 GB | $0.001097 |
| NVIDIA H200 | 141 GB | $0.001261 |
| NVIDIA B200 | 192 GB | $0.001736 |

CPU: $0.0000131 per core-second (min 0.125 cores). Memory: $0.00000222 per GiB-second. Volume storage: $0.09 per GiB-month (1 TiB free).

## Plans

| Plan | Monthly Fee | Included Credit | Containers | GPU Concurrency | Cron Jobs | Webhooks |
|---|---|---|---|---|---|---|
| Starter | $0 | $30 | 100 | 10 | 5 | 8 |
| Team | $250 | $100 | 1,000 | 50 | Unlimited | Unlimited |
| Enterprise | Custom | Custom | Custom | Custom | Custom | Custom |

## APIs

### Modal Functions API
Serverless Python functions backed by autoscaling container pools. Optional GPU attachment, declarative images, Volumes, Secrets, retries, timeouts, scheduling, dynamic batching, and class-based stateful workers. Invoke synchronously (`.remote()`), asynchronously (`.spawn()`), or as a map (`.map()`).

**Human URL:** [https://modal.com/docs/guide/apps](https://modal.com/docs/guide/apps)

- [Documentation — Apps](https://modal.com/docs/guide/apps)
- [Documentation — modal.Function](https://modal.com/docs/reference/modal.Function)
- [Documentation — modal.App](https://modal.com/docs/reference/modal.App)
- [OpenAPI](openapi/modal-functions-openapi.yml)
- [JSON Schema — Function](json-schema/modal-function-schema.json)
- [JSON-LD](json-ld/modal-com-context.jsonld)
- [Naftiko Capability — Functions](capabilities/functions-functions.yaml)

### Modal Sandboxes API
Secure containers for executing untrusted user or agent code. `Sandbox.create()` returns a long-lived isolated environment with `exec`, filesystem snapshots, port tunnels, volume mounts, GPU attachment, idle timeouts up to 24 h, readiness probes, named lookup, and tag-based filtering. The workhorse primitive for LLM coding agents on Modal.

**Human URL:** [https://modal.com/docs/guide/sandboxes](https://modal.com/docs/guide/sandboxes)

- [OpenAPI](openapi/modal-sandboxes-openapi.yml)
- [JSON Schema — Sandbox](json-schema/modal-sandbox-schema.json)
- [Naftiko Capability — Sandboxes](capabilities/sandboxes-sandboxes.yaml)

### Modal Volumes API
High-performance distributed file system optimized for ML workflows. `Volume.from_name()` attaches to Functions and Sandboxes with concurrent-read support, explicit `commit()` and `reload()` semantics, sub-path mounting, and read-only mounts. Volumes v2 (beta) removes inode limits and supports hundreds of concurrent writers to distinct files.

**Human URL:** [https://modal.com/docs/guide/volumes](https://modal.com/docs/guide/volumes)

- [OpenAPI](openapi/modal-volumes-openapi.yml)
- [Naftiko Capability — Volumes](capabilities/volumes-volumes.yaml)

### Modal Images API
Declarative, layered container image specifications built lazily on Modal's backend. Build from `debian_slim`, `micromamba`, `from_registry`, or `from_dockerfile`; layer `pip_install`, `apt_install`, `run_commands`, `env`, `copy_local_file`, and `copy_local_dir`. Modal caches layers globally so cold starts of identical images are sub-second.

**Human URL:** [https://modal.com/docs/guide/images](https://modal.com/docs/guide/images)

- [OpenAPI](openapi/modal-images-openapi.yml)
- [Naftiko Capability — Images](capabilities/images-images.yaml)

### Modal Secrets API
Encrypted, named bundles of environment variables injected into Functions and Sandboxes at runtime. Manage via dashboard, the `modal secret` CLI, or programmatically with `Secret.from_name()` / `Secret.from_dict()`.

**Human URL:** [https://modal.com/docs/guide/secrets](https://modal.com/docs/guide/secrets)

- [OpenAPI](openapi/modal-secrets-openapi.yml)
- [Naftiko Capability — Secrets](capabilities/secrets-secrets.yaml)

### Modal Dicts and Queues API
Distributed in-memory primitives. `modal.Dict` is a named key-value store; `modal.Queue` is a FIFO queue with optional partitioning and blocking gets. Both are addressable by name across Functions and Sandboxes for cross-container coordination.

**Human URL:** [https://modal.com/docs/guide/dicts](https://modal.com/docs/guide/dicts)

- [OpenAPI](openapi/modal-dicts-queues-openapi.yml)
- [Naftiko Capability — Dicts and Queues](capabilities/dicts-queues.yaml)

### Modal Schedules API
Periodic execution attached to a Function via `@app.function(schedule=modal.Cron(...))` or `modal.Period(...)`. Cron supports full cron syntax with timezone; Period specifies a fixed interval. Past runs appear in the dashboard with manual "run now" support.

**Human URL:** [https://modal.com/docs/guide/cron](https://modal.com/docs/guide/cron)

- [OpenAPI](openapi/modal-schedules-openapi.yml)
- [Naftiko Capability — Schedules](capabilities/schedules-schedules.yaml)

### Modal Web Endpoints API
Expose Functions over HTTP via `@modal.fastapi_endpoint`, `@modal.asgi_app` (FastAPI / Starlette / FastHTML), `@modal.wsgi_app` (Flask / Django), or `@modal.web_server` (any port-binding server). Supports streaming, WebSockets, proxy-auth tokens, custom URL labels, and live development via `modal serve`.

**Human URL:** [https://modal.com/docs/guide/webhooks](https://modal.com/docs/guide/webhooks)

- [OpenAPI](openapi/modal-web-endpoints-openapi.yml)
- [Naftiko Capability — Web Endpoints](capabilities/web-endpoints.yaml)

### Modal Tokens and Administration API
Token id/secret pair creation and revocation, environment management (e.g. `dev`/`staging`/`prod`), and workspace metadata. Tokens authenticate the `modal` CLI and the Python/TypeScript/Go SDKs against the control plane at `api.modal.com`.

**Human URL:** [https://modal.com/docs/reference/cli/token](https://modal.com/docs/reference/cli/token)

- [OpenAPI](openapi/modal-tokens-openapi.yml)
- [Naftiko Capability — Tokens and Administration](capabilities/tokens-administration.yaml)

## Common Properties

- [Portal — modal.com](https://modal.com)
- [Documentation — modal.com/docs](https://modal.com/docs)
- [GettingStarted](https://modal.com/docs/guide)
- [Examples Gallery](https://modal.com/docs/examples)
- [Python SDK Reference](https://modal.com/docs/reference)
- [Pricing](https://modal.com/pricing)
- [Blog](https://modal.com/blog)
- [ChangeLog](https://modal.com/changelog)
- [StatusPage](https://status.modal.com)
- [TermsOfService](https://modal.com/legal/terms)
- [PrivacyPolicy](https://modal.com/legal/privacy)
- [TrustCenter](https://trust.modal.com)
- [SignUp](https://modal.com/signup)
- [Support](https://modal.com/support)
- [Forum — Slack](https://modal.com/slack)
- [Twitter — @modal_labs](https://twitter.com/modal_labs)
- [LinkedIn](https://www.linkedin.com/company/modal-labs)
- [GitHubOrganization — modal-labs](https://github.com/modal-labs)
- [SDK — Python (modal-client)](https://github.com/modal-labs/modal-client)
- [SDK — TypeScript/Go (libmodal)](https://github.com/modal-labs/libmodal)
- [Package — modal on PyPI](https://pypi.org/project/modal/)
- [Package — modal on npm](https://www.npmjs.com/package/modal)
- [Tool — modal CLI](https://modal.com/docs/reference/cli/run)
- [CodeExamples — modal-examples](https://github.com/modal-labs/modal-examples)
- [CodeExamples — Multi-Node Training Guide](https://github.com/modal-labs/multinode-training-guide)
- [CodeExamples — QuiLLMan voice chat demo](https://github.com/modal-labs/quillman)
- [CodeExamples — Turbo Art (SDXL Turbo)](https://github.com/modal-labs/turbo-art)
- [CodeExamples — CI on Modal](https://github.com/modal-labs/ci-on-modal)
- [CodeExamples — Credential injection recipe](https://github.com/modal-labs/credential-injection)
- [Integrations — Vercel Integration example](https://github.com/modal-labs/vercel-integration-example)
- [Documentation — Modal GPU Glossary](https://github.com/modal-labs/gpu-glossary)
- [Tool — Stopwatch LLM benchmarking](https://github.com/modal-labs/stopwatch)
- [Documentation — Awesome Modal](https://github.com/modal-labs/awesome-modal)
- [Documentation — Synchronicity (async/sync interop)](https://github.com/modal-labs/synchronicity)
- [Documentation — GPU guide](https://modal.com/docs/guide/gpu)
- [Documentation — Scaling guide](https://modal.com/docs/guide/scale)
- [Documentation — Cold start guide](https://modal.com/docs/guide/cold-start)
- [Documentation — Memory snapshots](https://modal.com/docs/guide/memory-snapshots)
- [Documentation — Tunnels](https://modal.com/docs/guide/tunnels)
- [Documentation — Cloud bucket mounts](https://modal.com/docs/guide/cloud-bucket-mounts)
- [Documentation — Notebooks](https://modal.com/docs/guide/notebooks)
- [Documentation — Region selection](https://modal.com/docs/guide/region-selection)
- [Documentation — Private VPC](https://modal.com/docs/guide/private-vpc)
- [Documentation — Observability](https://modal.com/docs/guide/observability)
- [Documentation — Security](https://modal.com/docs/guide/security)

## Artifacts

Machine-readable API specifications organized by format.

### OpenAPI

- [Modal Functions API](openapi/modal-functions-openapi.yml)
- [Modal Sandboxes API](openapi/modal-sandboxes-openapi.yml)
- [Modal Volumes API](openapi/modal-volumes-openapi.yml)
- [Modal Images API](openapi/modal-images-openapi.yml)
- [Modal Secrets API](openapi/modal-secrets-openapi.yml)
- [Modal Dicts and Queues API](openapi/modal-dicts-queues-openapi.yml)
- [Modal Schedules API](openapi/modal-schedules-openapi.yml)
- [Modal Web Endpoints API](openapi/modal-web-endpoints-openapi.yml)
- [Modal Tokens and Administration API](openapi/modal-tokens-openapi.yml)

### JSON Schema

- [Modal Function Schema](json-schema/modal-function-schema.json)
- [Modal Sandbox Schema](json-schema/modal-sandbox-schema.json)

### JSON-LD

- [Modal Context](json-ld/modal-com-context.jsonld)

### Capabilities (Naftiko)

- [Functions](capabilities/functions-functions.yaml)
- [Sandboxes](capabilities/sandboxes-sandboxes.yaml)
- [Volumes](capabilities/volumes-volumes.yaml)
- [Images](capabilities/images-images.yaml)
- [Secrets](capabilities/secrets-secrets.yaml)
- [Dicts and Queues](capabilities/dicts-queues.yaml)
- [Schedules](capabilities/schedules-schedules.yaml)
- [Web Endpoints](capabilities/web-endpoints.yaml)
- [Tokens and Administration](capabilities/tokens-administration.yaml)

### Examples

- [Invoke Function](examples/modal-invoke-function-example.json)
- [Create Sandbox](examples/modal-create-sandbox-example.json)

### Vocabulary and Rules

- [Modal Vocabulary](vocabulary/modal-com-vocabulary.yml)
- [Modal Spectral Rules](rules/modal-rules.yml)

### Commercial artifacts

- [Plans / Pricing](plans/modal-plans-pricing.yml)
- [Rate Limits](rate-limits/modal-rate-limits.yml)
- [FinOps Definition](finops/modal-finops.yml)

## Maintainers

**FN:** Kin Lane

**Email:** info@apievangelist.com
