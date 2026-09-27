# Bitwarden and the Blackbox secrets TUI

Bitwarden remains the source of truth for passwords, TOTP codes, API
credentials, SSH keys, recovery codes, and license keys. The Blackbox tool is a
read-only access layer, not a second password manager.

## Planned TUI

`blackbox-secrets` will provide fuzzy search, username/password/TOTP copy,
URL opening, timed clipboard clearing, inactivity locking, and an optional
encrypted-file-vault mount control.

The first version must not edit, delete, export, or synchronize vault items.
It must never log secret values, put them in shell history, pass them as command
arguments, or write them to a local database.

## File vault boundary

Private documents use an encrypted folder under `~/Vaults/Blackbox/`. The
mounted plaintext view is temporary and must never be synchronized or added to
Git. Bitwarden and the file vault remain separate systems with separate
recovery procedures.

See the official [Bitwarden CLI documentation](https://bitwarden.com/help/cli/)
and [Bitwarden SSH Agent documentation](https://bitwarden.com/help/ssh-agent/)
for the underlying supported workflows.
