Vagrant.configure("2") do |config|

    config.vm.define "nginx" do |nginx_server|
      nginx_server.vm.provider :libvirt do |v|
        v.memory = 1024
      end
      nginx_server.vm.network "private_network", ip: "10.0.0.10"
      nginx_server.vm.box = "generic/ubuntu1804"
      nginx_server.vm.hostname = "nginx"
      nginx_server.vm.network "forwarded_port", guest: "80", host: "80"
      nginx_server.vm.provision "ansible" do |ansible|
        ansible.playbook = "provisioning/playbook.yaml"
      end

    end
  end
