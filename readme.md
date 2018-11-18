# Kubernetes cluster

A kubernetes cluster demo with 3 nodes (CentOS 7)

## Prerequisites
* Vagrant 2.2.0
* Ansible 2.7
* Virtualbox 5.2.20

## Deployment
Virtual machines creation

    vagrant up

Kubernetes installation

    ansible-galaxy install -r requirements.yml
    ansible-playbook -i environments/vagrant k8s.yml


