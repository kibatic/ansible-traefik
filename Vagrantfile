# Vagrantfile API/syntax version.
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "debian/jessie64"
  config.vm.hostname = "vagrant"
  config.vm.network "private_network", ip: "192.168.50.4"
  config.vm.provider :virtualbox do |virtualbox|
    virtualbox.name = "ansible-traefik"
  end
  config.vm.provision "ansible" do |ansible|
    ansible.sudo = true
    ansible.playbook = "tests/test.yml"
  end
end
