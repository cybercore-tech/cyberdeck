# SSH lockdown

SSH remains on its current port until the Blackbox migration is complete and
the replacement access path has been tested. Changing the port early creates a
needless recovery risk while storage, containers, backups, and credentials are
still being staged.

## Lockdown sequence

1. Confirm a second administrator key or physical recovery path.
2. Confirm key-based login from a separate terminal.
3. Add a validated `sshd_config.d` policy with root login disabled, password
   authentication disabled, public-key authentication required, and access
   limited to the intended user or group.
4. Disable forwarding features that are not required. Keep an explicit,
   documented exception if an SSH tunnel is genuinely needed.
5. Validate with `sshd -t`, reload the service, and test a new connection.
6. Open the replacement port in the firewall before changing the listener.
7. Test the replacement port from a second client, then remove the old port.

Never close the existing port until the replacement connection has completed a
real login and the recovery path has been tested.

## Recommended policy

- `PermitRootLogin no`
- `PasswordAuthentication no`
- `KbdInteractiveAuthentication no`
- `PubkeyAuthentication yes`
- `AuthenticationMethods publickey`
- `AllowUsers` or `AllowGroups` limited to the administration account
- `X11Forwarding no`
- `AllowAgentForwarding no`
- `MaxAuthTries 3`
- bounded login grace and client keepalive settings

Per-key restrictions should be used for automation keys where appropriate,
including disabling agent, X11, and TCP forwarding. Preserve TTY access only
for keys that need interactive administration.

## Recovery

Keep one existing administrative session open while validating the new policy.
If the replacement connection fails, restore the previous drop-in from the
console or the still-open session, validate it, and reload `sshd` before
closing the recovery session.
