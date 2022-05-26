# virt-host-playbooks
A collection of playbooks for setting up and configuring a libvirt host on Redhat Linux.

## Usage
```
git clone https://github.com/gsangwell/virt-host-playbooks.git
cd virt-host-playbooks
cp hosts_example.yaml hosts.yaml
vim hosts
ansible-playbook -i hosts.yaml setup-hosts.yaml
```
