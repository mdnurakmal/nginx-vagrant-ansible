Vagrant.configure("2") do |config|

    config.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--uart1", "0x3F8", "4"]
        vb.customize ["modifyvm", :id, "--uartmode1", "file", File::NULL]
    end
    config.ssh.insert_key = false

    config.vm.define "nginx" do |nginx_server|
      nginx_server.vm.box = "hashicorp/bionic64"
      nginx_server.vm.hostname = "nginx"
      nginx_server.vm.network "public_network"
      nginx_server.vm.network "forwarded_port", guest: "80", host: "8080"
      nginx_server.vm.provision "ansible" do |ansible|
        ansible.playbook = "ansible/nginx.yml"
        ansible.playbook = "ansible/sync.yml"
      end

    end
  end
