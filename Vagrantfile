# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.box_check_update = true
  config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
  config.vm.network "forwarded_port", guest: 1234, host: 1234, host_ip: "127.0.0.1"
  config.vm.network "private_network", ip: "192.168.33.10"

  config.disksize.size = '50GB'

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "4096"
    vb.cpus = 2

    # Enable nested VT-x
    vb.customize ["modifyvm", :id, "--nested-hw-virt", "on"]
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "Ansible/playbook.yml"
    ansible.install_mode = "default"
  end
end
