# This guide is optimized for Vagrant 1.7 and above.
# Although versions 1.6.x should behave very similarly, it is recommended
# to upgrade instead of disabling the requirement below.
Vagrant.require_version ">= 1.7.0"

Vagrant.configure(2) do |config|

  config.vm.box = "generic/ubuntu2004"
  config.vm.provider "hyperv"
  config.vm.network "public_network"
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  #config.vm.box_url = "https://app.vagrantup.com/generic/boxes/ubuntu2004/versions/4.0.2/providers/hyperv.box"

  # Disable the new default behavior introduced in Vagrant 1.7, to
  # ensure that all Vagrant machines will use the same SSH key pair.
  # See https://github.com/mitchellh/vagrant/issues/5005
  config.ssh.insert_key = false

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "playbook.yml"
  end
end
