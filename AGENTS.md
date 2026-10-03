# AGENTS

Bob-first execution is canonical for this repository. Read `BOB_EXECUTION_CANON_V1.md` before changing repository execution, automation, CI, or scheduling.

For ordinary work, inspect current repository state and `README.md`, then perform development and verification through Bob. GitHub is source control/history/review; GitHub Actions is exception-only.

Do not introduce GitHub Actions as general CI, cognition, scheduling, polling, watchdog, relay, or task infrastructure. A retained GitHub workflow requires an explicit repository-native KEEP rationale.
