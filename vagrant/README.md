# Ansible Collection - chadmf.vagrant

Simple collection to build multiple servers for Ansible testing including Rhel 8, rhel9, Centos8s Centos9s and fedora 36. Testing was done on all above operating systems as well.

Playbooks directory contains playbooks to run the roles.

## Getting Started

### Install the collection:

```shell
ansible-galaxy collection install git+https://github.com/chadmf/chadmf.vagrant
```

### Install dependencies

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