# SecurityLab storage layout

The system NVMe is reserved for the operating system and trusted Rust build
work. The encrypted `/home` device is reserved for personal data and existing
home subvolumes. Dedicated encrypted volumes are used for lab repositories,
container data, disposable VM disks, archives, and recovery templates.

Use stable filesystem identifiers and encrypted mappings. Never build fstab or
backup automation around an unqualified `/dev/sdX` name.

Large lab datasets and VM images must not be placed in the normal home tree
just because an empty directory exists there. Mount the dedicated lab volume at
the intended path first.
