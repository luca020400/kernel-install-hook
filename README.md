# kernel-install-hook

Automatically creates systemd-boot loader entries.

Make sure /{efi,boot}/$(cat /etc/machine-id) exists before installing.

Note: early microcode loading isn't supported.
