# Ansible-LVM
An Ansible playbook for disk and file system creation in RHEL.

# `lvm-operations.yml`
This playbook scans existing disks/filesystem on a RHEL VM using fstab. It then performs the following operations for each of the (`/dev/vd{b-g}`) devices that are present:
- creates a new partition
- creates a new LV
  - in the vg_root VG for RHEL 6
  - in the rhel VG for RHEL 7
- creates a file system
  - ext4 for RHEL 6
  - xfs for RHEL 7
- remounts the device
