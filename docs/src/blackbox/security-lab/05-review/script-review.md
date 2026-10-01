# Script and repository review

Treat every clone as data until reviewed.

## Review sequence

1. Clone without automatically building or executing.
2. Inspect the license, origin, recent activity, and dependency files.
3. Search for credential access, destructive commands, downloads, persistence,
   device access, shell evaluation, and network listeners.
4. Run language-specific static analysis.
5. Assign a trust tier.
6. Execute only inside the selected container or disposable VM.
7. Record the commit hash and review result.

Anything that captures input, modifies boot or kernel state, asks for broad
sudo, or attempts to hide its activity goes directly to the VM/quarantine
workflow.
