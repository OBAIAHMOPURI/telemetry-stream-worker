# Contributing to Telemetry Stream Worker

[Root README](README.md) · [Architecture](docs/ARCHITECTURE.md) · [Setup](docs/SETUP.md) · [API guide](docs/API.md) · [Network Ecosystem](README.md#network-ecosystem)

## Project status

This is a documentation-only worker concept. No broker, consumer, event schema, sink, runtime, checkpoint store, or automated test suite is implemented. Pipeline diagrams and delivery behavior are proposals; no live events are processed by this repository.

## Local workflow

Read the guides, agree a small change and acceptance criteria, then create a focused branch:

```sh
git clone https://github.com/OBAIAHMOPURI/telemetry-stream-worker.git
cd telemetry-stream-worker
git switch -c docs/describe-change
```

Use pull requests for normal review. This batch's explicit direct-to-main authorization is not a standing merge policy. Do not add guessed broker commands, package installs, or run instructions before selecting and implementing a stack.

## Repository-specific priorities

- Choose an input transport and durable sink, then define schema/versioning, stable event IDs, timestamps, ordering, retention, and redaction.
- Specify acknowledgement/checkpoint timing, replay and duplicate handling; do not promise exactly-once delivery without evidence.
- Design bounded retries, poison-message quarantine, dead-letter/manual recovery, graceful drain, and backpressure/resource limits.
- Treat any workflow/alert output as a separately implemented and approved integration, not an existing dependency.

## Quality and review evidence

Run `git diff --check` for documentation, inspect rendering, and verify root README/architecture/setup/API links and every sibling link. Keep current facts and future proposals distinct.

Future implementation changes should include reproducible local synthetic source/sink fixtures and tests for schema rejection, duplicates, out-of-order/replayed events, poison messages, sink failure, bounded memory, checkpoint recovery, shutdown, and sensitive-data redaction. Record exact commands/versions, observed outcomes, and tests not run. No existing CI or passing test suite is implied. Pull requests should explain scope, data/compatibility impacts, evidence, unresolved decisions, migration/replay risks, and rollback/recovery behavior; update contracts and setup with changes.

## Data and operational safety

Never commit broker credentials, keys, production telemetry, identifying payloads, private operational notes, or unredacted logs. Use synthetic data and sandbox systems. Sensitive reports belong in an owner-approved private channel. Live event consumption, retention changes, external integrations, and infrastructure/deployment changes need separate authorization. No license is selected here.

## Sibling repository network

Navigation only; no event pipeline or live integrations are claimed.

- [alert-notification-dispatcher](https://github.com/OBAIAHMOPURI/alert-notification-dispatcher/blob/main/README.md)
- [Brainwave_Matrix_Intern — Banky Application](https://github.com/OBAIAHMOPURI/Brainwave_Matrix_Intern/blob/main/README.md)
- [BrainWave_Matrix_Intern1 — Hospital Management System](https://github.com/OBAIAHMOPURI/BrainWave_Matrix_Intern1/blob/main/README.md)
- [edge-gateway-service](https://github.com/OBAIAHMOPURI/edge-gateway-service/blob/main/README.md)
- [edge-gateway-service1](https://github.com/OBAIAHMOPURI/edge-gateway-service1/blob/main/README.md)
- [identity-auth-proxy](https://github.com/OBAIAHMOPURI/identity-auth-proxy/blob/main/README.md)
- [workflow-state-sync](https://github.com/OBAIAHMOPURI/workflow-state-sync/blob/main/README.md)
