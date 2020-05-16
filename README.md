# Vagrant
Getting started with Vagrant.

# Mult-machine:
This article is step by step explain for getting multi-VM setup where the VMs can talk to each other.

## Goal:
We’ll have 3 virtual machines, one called “master” and two nodes, that can find each other via their hostnames. Except for Vagrant, no external software is required to achieve this.

The setup we’ll be creating is just a foundation you can expand on. It won’t do anything meaningful. It’s just to get you the infrastructure to do something meaningful.

If you’re just interested in the end result, skip ahead to Putting everything together.

## Initial step:
- vagrant init hashicorp/precise64
- vagrant up
- vagrant ssh
- vagrant destroy -f