Vagrant.configure("2") do |config|

    config.vm.define "nginx" do |nginx_server|
      nginx_server.vm.box = "hashicorp/bionic64"
      nginx_server.vm.hostname = "nginx"
      nginx_server.vm.network "private_network", type: "dhcp",
        name: "vboxnet3"
      nginx_server.vm.network "forwarded_port", guest: "80", host: "8080"
      nginx_server.vm.provision "ansible" do |ansible|
        ansible.playbook = "ansible/nginx.yml"
        ansible.playbook = "ansible/sync.yml"
      end

    end
  end
