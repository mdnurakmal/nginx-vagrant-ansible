
# Automatically create nginx server using vagrant , libvirt, ansible

# Development Environment
- Running on Ubuntu 20.04 (LTS) x64 on droplet from digitalocean

# Installation
Install libvirt
```shell
sudo apt install qemu qemu-kvm libvirt-clients libvirt-daemon-system virtinst bridge-utils -y
sudo apt-get update -y
sudo systemctl enable libvirtd
sudo apt install qemu libvirt-daemon-system libvirt-clients libxslt-dev libxml2-dev libvirt-dev zlib1g-dev ruby-dev ruby-libvirt ebtables dnsmasq-base -y
```

Install vagrant
```shell
sudo apt install vagrant -y
```

Install ansible
```shell
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible -y
```

## Usage

Create VMs from vagrant file

```shell
vagrant up
```

Check nginx website can be access from host pc that is running vagrant

```shell
curl localhost:8080
```

Destroy VMs

```shell
vagrant destroy
```
# Learning objective
* Ansible basics

# Learning Points
* Running vagrant on ubuntu using droplet from digitalocean since ansible is not supported on windows platform
* How to fix "vagrant up stuck at SSH auth method" ? (Use libvirt instead of virtual box)
* add host_ip = "*" to forwarded_port inside vagrantfile
* How to automate all the prerequisite installation on host pc before running vagrant ? (Terraform ?)

# References
* https://ostechnix.com/install-and-configure-kvm-in-ubuntu-20-04-headless-server/
* https://ostechnix.com/how-to-use-vagrant-with-libvirt-kvm-provider/
