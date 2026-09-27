# Disposable VM runbook

Use KVM/libvirt for unknown binaries, penetration-testing targets, exploit
development, kernel or driver work, input-capture tests, and anything requiring
sudo inside the guest.

## Guest defaults

1. Start from a known ISO and record its checksum.
2. Use a disposable copy-on-write disk.
3. Start with NAT or an isolated virtual network.
4. Disable shared folders, clipboard, SSH-agent forwarding, and USB passthrough.
5. Take a clean snapshot before testing.
6. Revert or destroy the guest after the experiment.
7. Record the scope, commands, hashes, and outcome.

Never bridge a test VM onto a network you do not own or have explicit permission
to test.
