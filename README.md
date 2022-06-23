# virt-host-playbooks
A collection of playbooks for setting up and configuring a libvirt host on Redhat Linux.

## Usage
```
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
ansible-playbook -e vmhost=<HOSTNAME> vmvars=vms.yaml setup-vms.yaml
```
