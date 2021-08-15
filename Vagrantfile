Vagrant.configure("2") do |config|

    config.vm.define "nginx" do |nginx_server|
      nginx_server.vm.provider :libvirt do |v|
        v.memory = 1024
      end
      nginx_server.vm.network :public_network
      nginx_server.vm.box = "generic/ubuntu1804"
      nginx_server.vm.hostname = "nginx"
      nginx_server.vm.network "forwarded_port", guest: "80", host: "8080"
      nginx_server.vm.provision "ansible" do |ansible|
        ansible.playbook = "provisioning/playbook.yml"
      end

    end
  end
