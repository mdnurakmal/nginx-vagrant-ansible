Vagrant.configure("2") do |config|
   #  config.vm.provider "virtualbox" do |vb|
   #    # Display the VirtualBox GUI when booting the machine
   #    # vb.gui = true
   #
   #    # Customize the amount of memory on the VM:
   #    vb.memory = "1024"
   #
   #    vb.customize ["modifyvm", :id, "--uart1", "0x3F8", "4"]
   #    vb.customize ["modifyvm", :id, "--uartmode1", "file", File::NULL]
   #
   #    vb.customize ["modifyvm", :id, "--nestedpaging", "off"]
   #    vb.customize ["modifyvm", :id, "--cpus", 4]
   #    vb.customize ["modifyvm", :id, "--paravirtprovider", "hyperv"]
   #    vb.customize ["modifyvm", :id, "--cableconnected1", "on"]
   # end

    config.vm.define "nginx" do |nginx_server|
      nginx_server.vm.box = "ubuntu/trusty64"
      nginx_server.vm.hostname = "nginx"
      nginx_server.vm.network "forwarded_port", guest: "80", host: "8080"
      nginx_server.vm.provision "ansible" do |ansible|
        ansible.playbook = "ansible/nginx.yml"
        ansible.playbook = "ansible/sync.yml"
      end

    end
  end
