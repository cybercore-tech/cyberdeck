# Blackbox SecurityLab

SecurityLab is a controlled environment for security research, penetration
testing, OSINT tooling, static analysis, and disposable experiments.

The trusted host remains focused on Rust development. Reviewed utilities may
run in rootless containers. Unknown, privileged, kernel-facing, or input
capture workloads belong in disposable virtual machines.

## Documentation map

- [Architecture](00-overview/architecture.md)
- [Storage layout](01-storage/layout.md)
- [Container policy](02-containers/policy.md)
- [Virtual-machine runbook](03-virtual-machines/runbook.md)
- [OSINT workflow](04-osint/workflow.md)
- [Script review](05-review/script-review.md)
- [Backup boundaries](06-backup/boundaries.md)
- [Incident response](07-operations/incident-response.md)
- [Bitwarden and Blackbox TUI](08-secrets/bitwarden-tui.md)

## Trust rule

> If a workload needs host devices, privileged networking, sudo, kernel access,
> input capture, or an unknown binary payload, use a disposable VM.
