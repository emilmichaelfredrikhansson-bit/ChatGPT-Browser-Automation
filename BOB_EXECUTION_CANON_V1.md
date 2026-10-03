# Bob Execution Canon V1

Effective: 2026-10-03

## Decision

Bob is the default execution/control plane for this repository. GitHub is source control, history, pull-request/review surface and an exception-only trust/repository-native effect boundary; GitHub Actions is not the default scheduler, task queue, cognition host, watchdog, relay, polling loop, or general-purpose compute layer.

## Default routing

1. Operator-present repository development, maintenance and verification runs through Bob.
2. Unattended recurring/conditional/background cognition runs as Bob Tasks.
3. Deterministic always-on provider/data runtime that should not depend on the operator computer runs on an appropriate managed runtime (for example Supabase, Hugging Face Jobs, Cloudflare, or another project-qualified service), with repository changes and operational control routed through Bob.
4. GitHub Actions may remain only when GitHub itself is the natural trust/effect boundary and the workflow has an explicit documented KEEP rationale.

## Development verification

Bob performs the main deterministic verification locally before push. Automatic GitHub CI fan-out is non-canonical. A project may retain at most a small independent remote gate when it materially adds assurance that Bob/local verification cannot provide.

## Workflow lifecycle

Every existing or proposed GitHub workflow must be classified as exactly one of:

- RETIRE
- MOVE_TO_BOB
- MOVE_TO_MANAGED_RUNTIME
- KEEP

Default is not KEEP. A new or retained automatic GitHub workflow requires a concrete repository-native rationale.

## Prohibited default patterns

Do not introduce new GitHub Actions for:

- periodic wake/check loops;
- Scheduled-Task replacement;
- cognition or agent execution;
- task prepare/result/watchdog relays;
- ordinary local lint/test/build loops;
- polling/recovery loops;
- generic provider acquisition or data processing.

## Authority and safety

Bob-first routing does not expand effect authority. Deploys, production mutation, secrets, material spend, destructive administration and other material external effects remain separately bounded by project authority.

One semantic work item has one active executor. When a workload moves, retire or disable the replaced path before enabling a second primary writer.

## Supersession

This canon supersedes older repository guidance that treats GitHub Actions or native Scheduled Tasks as the default execution path. Historical workflows may remain as evidence or manual rollback surfaces until safely retired, but they are not the forward architecture.
