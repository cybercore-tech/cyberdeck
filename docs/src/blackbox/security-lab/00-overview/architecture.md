# SecurityLab architecture

## Trust tiers

| Tier | Environment | Examples | Network |
| --- | --- | --- | --- |
| 0 | Trusted host | Rust, editor, reviewed utilities | Normal host network |
| 1 | Rootless container | Static analysis, reviewed CLI tools | None by default |
| 2 | OSINT container | Approved collection tools | Explicit user-mode network |
| 3 | Disposable VM | Unknown code, exploits, kernel/input work | NAT or isolated lab network |

## Hard boundaries

Lab workloads must not receive the host home directory, SSH agent, browser
profiles, credential stores, Docker socket, arbitrary `/dev` access, host PID or
IPC namespaces, or unrestricted sudo.

The lab is a place to reduce blast radius, not a reason to weaken the host.
