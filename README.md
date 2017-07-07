# Proxmox - DRBD9 Ansible Playbook
It's a playbook that automates Proxmox and DRBD9 installation with Ansible on two or more nodes.
The two roles of playbook follow the official documentation of DRBD9 and Proxmox.

In group_vars folder, you can set a disk( **/dev/sdX**) or a list of disks which are the physical volumes of volume group.
```yaml
---
drbd_disks:
  - /dev/vdx
  - /dev/vdy
```
The execution of playbook is:
```
ansible-playbook -u your_user main.yml -e target=name_of_prefix_you_gave_in_inventory -e drbd_volume_size=number_of_Gigabytes
```
*Note: This installation is compatible only for Proxmox 4.4. DRBD9 doesn't work with Proxmox5, because  there isn't repository for this yet*
