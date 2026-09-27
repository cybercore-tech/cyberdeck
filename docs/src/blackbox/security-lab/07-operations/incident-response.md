# SecurityLab incident response

If a tool behaves unexpectedly:

1. Stop the container or VM.
2. Disconnect its lab network.
3. Do not open the artifact on the trusted host.
4. Record the image, guest snapshot, repository commit, and timestamps.
5. Preserve hashes and logs in the case workspace.
6. Rotate any credential that may have been exposed.
7. Rebuild the disposable environment from a known baseline.

If the host itself may be affected, stop experimentation, lock the vault,
disconnect from networks as appropriate, and use an independent recovery path.
