# virt-host-playbooks
A collection of playbooks for setting up and configuring a libvirt host on Redhat Linux.

## Requirements
```
python36
libvirt-python3
python3-lxml
ansible
```

## Usage
```
sudo su -
git clone https://github.com/gsangwell/virt-host-playbooks.git
cd virt-host-playbooks
ansible-galaxy install -r requirements.yaml
cp hosts_example.yaml hosts.yaml
vim hosts.yaml
ansible-playbook -i hosts.yaml setup-hosts.yaml
```

## Create VMs
```
cp vms_example.yaml vms.yaml
vim vms.yaml
ansible-playbook -i hosts.yaml vmvars=vms.yaml setup-vms.yaml

# Create multiple yaml files for different sets of VMs
cp vms_example.yaml newvms.yaml
ansible-playbook -i hosts.yaml -e vmvars=newvms.yaml setup-vms.yaml
```

## Deleting VMs
Currently no playbook to delete VMs, so this needs to be done manually using virsh commands.
```
virsh destroy <vm_name>
virsh undefine <vm_name>
virsh vol-delete <vm_name>-<volume_name>.<vol_format> --pool <vol_pool>
```
