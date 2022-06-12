Vagrant.require_version ">= 1.7.0"

Vagrant.configure(2) do |config|
  config.vm.box = "generic/ubuntu2004"
  config.vm.provider "virtualbox"
  config.vm.network "public_network"
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.ssh.insert_key = false

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
