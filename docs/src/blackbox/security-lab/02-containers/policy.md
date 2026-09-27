# Rootless container policy

Containers are appropriate for reviewed tools and static analysis. They are not
an adequate boundary for unknown code that requests host devices or elevated
privileges.

## Required defaults

- Rootless runtime;
- read-only root filesystem;
- all capabilities dropped;
- `no-new-privileges`;
- bounded memory, CPU, and process count;
- isolated temporary filesystem;
- no host Docker socket;
- no home-directory mount;
- no devices unless explicitly documented;
- no network unless explicitly requested.

Builds and tool execution should happen from a reviewed clone under the lab
repository directory. Do not install cloned tools globally or add them to the
host `$PATH`.
