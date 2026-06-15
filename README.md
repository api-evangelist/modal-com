# Modal (modal)

Modal is a serverless cloud platform for AI and data workloads. Modal lets developers write ordinary Python and run it on remote GPUs and CPUs with sub-second cold starts, instant autoscaling, and declarative container images. The platform's primitives — Functions, Sandboxes, Volumes, Images, Secrets, Dicts, Queues, Schedules, and Web Endpoints — cover inference, fine-tuning, multi-node training, batch processing, agent code execution, and HTTP/web APIs. Modal sells per-second metered compute across the full NVIDIA GPU lineup (T4 → B200) under Starter, Team, and Enterprise plans. Modal Labs raised a $355M Series C in 2026 and is used in production by Decagon, Runway, Physical Intelligence, Suno, Chai Discovery, Lovable, Quora, Reducto, and many others.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/modal-com/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/modal-com/refs/heads/main/apis.yml)

## Scope

- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- Serverless
- GPU
- Cloud Compute
- AI Infrastructure
- Sandboxes
- Inference
- Training
- Batch Processing
- Python
- TypeScript
- Go

## Timestamps

- **Created:** 2026-05-25T00:00:00.000Z
- **Modified:** 2026-05-25

## APIs

### Modal Functions API

Modal Functions are the core serverless primitive — Python functions backed by autoscaling container pools. They support optional GPU attachment (T4 through B200), Modal-built container images, Volumes, Secrets, retries, timeouts, scheduling, web endpoints, dynamic batching, and class-based stateful workers. Invoke synchronously (`.remote()`), asynchronously (`.spawn()`), or as a map (`.map()`).

- **Human URL:** [https://modal.com/docs/guide/apps](https://modal.com/docs/guide/apps)

#### Tags

- Serverless
- GPU
- Functions
- Python

#### Properties

- [Documentation](https://modal.com/docs/guide/apps)
- [Documentation](https://modal.com/docs/reference/modal.Function)
- [Documentation](https://modal.com/docs/reference/modal.App)
- [OpenAPI](openapi/modal-functions-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/modal-functions.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/modal-functions.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/modal-function-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/modal-com-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)

### Modal Sandboxes API

Modal Sandboxes are secure containers for executing untrusted user or agent code. Spawned at runtime with `Sandbox.create()`, they support arbitrary command execution, filesystem snapshots, port tunnels, volume mounts, GPU attachment, idle timeouts (up to 24h), readiness probes, named lookup, and tagging. Sandboxes are the workhorse primitive for LLM coding agents and rollout systems on Modal.

- **Human URL:** [https://modal.com/docs/guide/sandboxes](https://modal.com/docs/guide/sandboxes)

#### Tags

- Sandboxes
- Agents
- Code Execution
- Isolation

#### Properties

- [Documentation](https://modal.com/docs/guide/sandboxes)
- [Documentation](https://modal.com/docs/reference/modal.Sandbox)
- [OpenAPI](openapi/modal-sandboxes-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/modal-sandboxes.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/modal-sandboxes.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/modal-sandbox-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Modal Volumes API

Modal Volumes provide a high-performance distributed file system optimized for ML workflows. Volumes attach to Functions and Sandboxes via `Volume.from_name()`, support concurrent reads, explicit `commit()` and `reload()` semantics, sub-path mounting, and read-only mounts. Volumes v2 (beta) removes inode limits and supports hundreds of concurrent writers to distinct files.

- **Human URL:** [https://modal.com/docs/guide/volumes](https://modal.com/docs/guide/volumes)

#### Tags

- Storage
- Distributed File System
- Persistence

#### Properties

- [Documentation](https://modal.com/docs/guide/volumes)
- [Documentation](https://modal.com/docs/reference/modal.Volume)
- [OpenAPI](openapi/modal-volumes-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/modal-volumes.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/modal-volumes.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Modal Images API

Modal Images are declarative, layered container image specifications built lazily on Modal's backend. Build from `debian_slim`, `micromamba`, `from_registry`, or `from_dockerfile`; layer `pip_install`, `apt_install`, `run_commands`, `env`, `copy_local_file`, and `copy_local_dir`. Modal caches layers globally so cold starts of identical images are sub-second.

- **Human URL:** [https://modal.com/docs/guide/images](https://modal.com/docs/guide/images)

#### Tags

- Container Images
- Build
- Python

#### Properties

- [Documentation](https://modal.com/docs/guide/images)
- [Documentation](https://modal.com/docs/reference/modal.Image)
- [OpenAPI](openapi/modal-images-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/modal-images.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/modal-images.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Modal Secrets API

Modal Secrets are encrypted, named bundles of environment variables injected into Functions and Sandboxes at runtime. Manage via dashboard, the `modal secret` CLI, or programmatically with `Secret.from_name()` / `Secret.from_dict()`.

- **Human URL:** [https://modal.com/docs/guide/secrets](https://modal.com/docs/guide/secrets)

#### Tags

- Secrets
- Configuration
- Environment Variables

#### Properties

- [Documentation](https://modal.com/docs/guide/secrets)
- [Documentation](https://modal.com/docs/reference/modal.Secret)
- [OpenAPI](openapi/modal-secrets-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/modal-secrets.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/modal-secrets.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Modal Dicts and Queues API

Modal Dicts and Queues are distributed in-memory primitives. `modal.Dict` is a named key-value store; `modal.Queue` is a FIFO queue with optional partitioning and blocking gets. Both are addressable by name across Functions and Sandboxes for cross-container coordination.

- **Human URL:** [https://modal.com/docs/guide/dicts](https://modal.com/docs/guide/dicts)

#### Tags

- Dicts
- Queues
- State
- Coordination

#### Properties

- [Documentation](https://modal.com/docs/guide/dicts)
- [Documentation](https://modal.com/docs/guide/queues)
- [Documentation](https://modal.com/docs/reference/modal.Dict)
- [Documentation](https://modal.com/docs/reference/modal.Queue)
- [OpenAPI](openapi/modal-dicts-queues-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/modal-dicts-queues.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/modal-dicts-queues.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Modal Schedules API

Modal Schedules attach periodic execution to a Function via `@app.function(schedule=modal.Cron(...))` or `modal.Period(...)`. Cron supports full cron syntax with timezone; Period specifies a fixed interval. Past runs appear in the dashboard with manual "run now" support.

- **Human URL:** [https://modal.com/docs/guide/cron](https://modal.com/docs/guide/cron)

#### Tags

- Cron
- Scheduling
- Recurring Jobs

#### Properties

- [Documentation](https://modal.com/docs/guide/cron)
- [OpenAPI](openapi/modal-schedules-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/modal-schedules.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/modal-schedules.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Modal Web Endpoints API

Modal Web Endpoints expose Functions over HTTP via `@modal.fastapi_endpoint`, `@modal.asgi_app` (FastAPI/Starlette/FastHTML), `@modal.wsgi_app` (Flask/Django), or `@modal.web_server` (any port-binding server). Supports streaming, WebSockets, proxy-auth tokens, custom URL labels, and live development via `modal serve`.

- **Human URL:** [https://modal.com/docs/guide/webhooks](https://modal.com/docs/guide/webhooks)

#### Tags

- Web
- HTTP
- ASGI
- WSGI
- FastAPI

#### Properties

- [Documentation](https://modal.com/docs/guide/webhooks)
- [Documentation](https://modal.com/docs/guide/webhook-urls)
- [Documentation](https://modal.com/docs/guide/webhook-proxy-auth)
- [OpenAPI](openapi/modal-web-endpoints-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/modal-web-endpoints.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/modal-web-endpoints.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Modal Tokens and Administration API

Administrative surface for Modal — token id/secret pair creation and revocation, environment management (e.g. `dev`/`staging`/`prod`), and workspace metadata. Tokens authenticate the `modal` CLI and the Python/TypeScript/Go SDKs against the control plane at `api.modal.com`.

- **Human URL:** [https://modal.com/docs/reference/cli/token](https://modal.com/docs/reference/cli/token)

#### Tags

- Administration
- Tokens
- Workspaces
- Environments

#### Properties

- [Documentation](https://modal.com/docs/reference/cli/token)
- [Documentation](https://modal.com/docs/reference/cli/profile)
- [Documentation](https://modal.com/docs/guide/environments)
- [OpenAPI](openapi/modal-tokens-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/modal-tokens.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/modal-tokens.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Portal](https://modal.com)
- [Documentation](https://modal.com/docs)
- [Getting Started](https://modal.com/docs/guide)
- [Code Examples](https://modal.com/docs/examples)
- [Documentation](https://modal.com/docs/reference)
- [Blog](https://modal.com/blog)
- [Changelog](https://modal.com/changelog)
- [Status Page](https://status.modal.com)
- [Terms of Service](https://modal.com/legal/terms)
- [Privacy Policy](https://modal.com/legal/privacy)
- [Trust Center](https://trust.modal.com)
- [Sign Up](https://modal.com/signup)
- [Sign Up](https://modal.com/login)
- [Support](https://modal.com/support)
- [Forum](https://modal.com/slack)
- [Twitter](https://twitter.com/modal_labs)
- [LinkedIn](https://www.linkedin.com/company/modal-labs)
- [GitHub Organization](https://github.com/modal-labs)
- [SDK](https://github.com/modal-labs/modal-client)
- [SDK](https://github.com/modal-labs/libmodal)
- [Code Examples](https://github.com/modal-labs/modal-examples)
- [Code Examples](https://github.com/modal-labs/multinode-training-guide)
- [Documentation](https://github.com/modal-labs/awesome-modal)
- [Tool](https://github.com/modal-labs/synchronicity)
- [Code Examples](https://github.com/modal-labs/quillman)
- [Code Examples](https://github.com/modal-labs/turbo-art)
- [Code Examples](https://github.com/modal-labs/ci-on-modal)
- [Integrations](https://github.com/modal-labs/vercel-integration-example)
- [Code Examples](https://github.com/modal-labs/credential-injection)
- [Documentation](https://github.com/modal-labs/gpu-glossary)
- [Tool](https://github.com/modal-labs/stopwatch)
- [Package](https://pypi.org/project/modal/)
- [Package](https://www.npmjs.com/package/modal)
- [Tool](https://modal.com/docs/reference/cli/run)
- [Documentation](https://modal.com/docs/guide/gpu)
- [Documentation](https://modal.com/docs/guide/scale)
- [Documentation](https://modal.com/docs/guide/cold-start)
- [Documentation](https://modal.com/docs/guide/memory-snapshots)
- [Documentation](https://modal.com/docs/guide/retries)
- [Documentation](https://modal.com/docs/guide/timeouts)
- [Documentation](https://modal.com/docs/guide/preemption)
- [Documentation](https://modal.com/docs/guide/tunnels)
- [Documentation](https://modal.com/docs/guide/cloud-bucket-mounts)
- [Documentation](https://modal.com/docs/guide/notebooks)
- [Documentation](https://modal.com/docs/guide/private-vpc)
- [Documentation](https://modal.com/docs/guide/region-selection)
- [Documentation](https://modal.com/docs/guide/managing-deployments)
- [Documentation](https://modal.com/docs/guide/observability)
- [Documentation](https://modal.com/docs/guide/security)
- [Plans](https://modal.com/pricing)
- [Pricing](https://modal.com/pricing)
- [Plans](plans/modal-plans-pricing.yml)
- [Rate Limits](rate-limits/modal-rate-limits.yml)
- [Fin Ops](finops/modal-finops.yml)
- [Vocabulary](vocabulary/modal-com-vocabulary.yml)
- [Spectral Rules](rules/modal-rules.yml)
- [Features](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
