# Ansible-LVM
An  Ansible playbook for disk and file system creation in RHEL

# create_filesystem
This playbook scans existing disks/filesystem on a RHEL VM using fstab.  It then creates a new partition, LV, and file system

## Dependencies
- RHEL 6 VM - Creates a ext4 file system in the "vg_root" volume group
- RHEL 7 VM - Creates a xfs file system in the "rhel" volume group

## Role: create_filesystem

### Vars

### Tasks
- Scan /etc/fstab for disks and add to array
- Unmount file systems from array
- Create new partition on each disk in array
- Create new logical volume on each new partition
- Add new LV to existing volume group
- Create new ext4 or xfs file system (based on VG and RHEL version)
- Add new file system to /etc/fstab
