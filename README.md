# Ansible Collection - chadmf.vagrant

Simple collection to build multiple servers for Ansible testing including Rhel 8, rhel9, Centos9s and fedora 36. Testing was done on all above operating systems as well. This will also set up ~/.ansible.cfg to use the inventory file it creates in ~/vagrant/inventory.ini. Hopefully turn key lab environment. All comments are welcome via PR or issues!

Playbooks directory contains playbooks to run the roles.

## Getting Started

### Install the collection

```shell
ansible-galaxy collection install git+https://github.com/chadmf/chadmf.vagrant
```

### Install everything in one playbook

Does all of the things below (besides the destroy and cleanup) to spin up 4 small vms for testing. **NOTE**: this assumes you have an inventory file with [all] in it. If you do not you may want to change the all to localhost to run locally in the playbook.

```shell
ansible-playbook playbooks/vagrant_all.yml
```

### Install dependencies

Uses dnf module to install qemu-kvm and other dependencies needed for Vagrant.

```shell
ansible-playbook playbooks/vagrant_install.yml
```

### Configure directories and Vagrantfiles

This will create directories in /home/{{ ansible_user_id }}/vagrant/osname as well as run vagrant init to create the Vagrantfile

```shell
ansible-playbook playbooks/vagrant_config.yml
```

### Vagrant up

Starts the vms

```shell
ansible-playbook playbooks/vagrant_up.yml
```

### Vagrant down

Stops the vm

```shell
ansible-playbook playbooks/vagrant_down.yml
```

### Vagrant destroy

Destroys the vms

```shell
ansible-playbook playbooks/vagrant_destroy.yml
```

### Vagrant cleanup

Removes all vagrant directories and ssh configs. Should do this with destroy but sometimes things fail...

```shell
ansible-playbook playbooks/vagrant_cleanup.yml
```
