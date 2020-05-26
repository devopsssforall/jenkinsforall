# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/bionic64"

  config.vm.define :client do |devopsss_demo|
      devopsss_demo.vm.host_name = "devopsssforall"
      devopsss_demo.vm.network "private_network", ip:"192.168.100.10"
      devopsss_demo.vm.network "forwarded_port", guest: 22, host: 2222, auto_correct: true
      devopsss_demo.vm.network "forwarded_port", guest: 8080, host: 8080, auto_correct: true
      devopsss_demo.vm.provision "shell", path: "install_jenkins.sh"
      devopsss_demo.vm.provider :virtualbox do |vb|
          vb.customize ["modifyvm", :id, "--memory", "2048"]
          vb.customize ["modifyvm", :id, "--cpus", "1"]
      end
  end
end