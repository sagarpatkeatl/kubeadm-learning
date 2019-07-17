# Kubernetes with Authentication and RBAC

This repository provides scripts to provision and configure VMs, so that we can
play with kubeadm tool without distractions. It configures three VMs, so as to
allow for convenient multi-node cluster setup.

## Prerequisites

To work correctly, it depends on the following tools

1. Git
1. Virtualbox
1. Vagrant
1. Ansible

## Files

- `Vagrantfile` - This provides the VM definitions for three VMs with Host-Only networking
- `playbook.yml` - Ansible playbook for configuring hostnames 
- `roles.yml` - The roles required in `playbook.yml`
- `samples` - Some useful sample cluster spec (kubeadm) and configuration manifests (kubectl)

## Setup Instructions

1. Ensure all prerequisites are met
1. Clone this repository: `git clone https://github.com/sagarpatkeatl/kubeadm-learning`, and cd into it: `cd kubeadm-learning`
1. Install ansible role depenencies: `ansible-galaxy install -r roles.yml -p roles`
1. You may now start one or all three virtual machines
   - `vagrant up` starts and provisions all virtual machines. Creates following three virtual machines
    - `node1` - 192.168.100.11
    - `node2` - 192.168.100.12
    - `node3` - 192.168.100.13

## Other useful commands

- `vagrant up node1` starts and provisions only node1, and vice versa
- `vagrant ssh node1` ssh to node1
- `vagrant ssh node1 -c "sudo kubeadm config images pull"` - Execute a command in node1
- `vagrant destroy` - to destroy all nodes

## Contribute

1. Provide useful samples as pull requests
1. Report bugs / improvements
