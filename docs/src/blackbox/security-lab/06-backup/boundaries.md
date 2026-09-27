# SecurityLab backup boundaries

A local mirror is not a complete backup and a backup can preserve unsafe data.

## Include after review

- source repositories and lockfiles;
- lab configuration and container definitions;
- reports, notes, hashes, and approved case exports;
- clean VM templates and recovery documentation.

## Exclude by default

- container image layers and caches;
- build targets and package caches;
- raw downloads and quarantined binaries;
- browser sessions and cookies;
- mounted plaintext secret folders;
- temporary logs and disposable VM disks.

Back up encrypted ciphertext for private files. Never back up the mounted
plaintext secrets view.

An off-site provider such as MEGA should use historical backup behavior rather
than a two-way sync for critical data. Keep the provider’s recovery material
offline and test restores into a temporary directory.
