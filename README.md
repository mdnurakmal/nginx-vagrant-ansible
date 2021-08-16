
# Automatically create nginx server using vagrant , virtualbox , chef-solo

# Development Environment
- Ubuntu 20.04 (LTS) x64

# Installation

Download & Install:
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads) (latest version, tested with 6.1.22)
- [Vagrant](https://www.vagrantup.com/downloads.html) (latest version, tested with 2.2.18)

```shell
sudo apt update
sudo apt install virtualbox
sudo curl -O https://releases.hashicorp.com/vagrant/2.2.18/vagrant_2.2.18_x86_64.deb
sudo apt install ./vagrant_2.2.18_x86_64.deb
```

- [Ansible] (latest version, tested with 2.10)
Allow SSH for firewall
```shell
sudo apt-add-repository ppa:ansible/ansible-2.10
sudo ufw allow 22
```

## Usage

Create VMs from vagrant file

```shell
vagrant up
```

Check nginx is running by entering 10.0.0.10 into your browser

Destroy VMs

```shell
vagrant destroy
```
# Learning objective

# Learning Points
* By default libvirt create VM on Nat
* Running vagrant on ubuntu using droplet from digitalocean
* How to fix "vagrant up stuck at SSH auth method"

# References
* https://ostechnix.com/install-and-configure-kvm-in-ubuntu-20-04-headless-server/
* https://ostechnix.com/how-to-use-vagrant-with-libvirt-kvm-provider/
