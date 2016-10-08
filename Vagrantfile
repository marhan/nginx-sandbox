# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "geerlingguy/ubuntu1604"
  config.ssh.insert_key = false

  config.vm.provider :virtualbox do |v|
    v.name = "sandbox"
    v.memory = 512
    v.cpus = 2
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  config.vm.define "sandbox" do |sandbox|
    sandbox.vm.hostname = "sandbox"
    sandbox.vm.network :private_network, ip: "192.168.33.33"

    sandbox.vm.provision :ansible do |ansible|
      ansible.playbook = "provisioning/sandbox/playbook.yml"
      ansible.inventory_path = "provisioning/sandbox/inventory"
      ansible.sudo = true
    end
  end

  if Vagrant.has_plugin?("vagrant-cachier")
    config.cache.scope = :box
  end

end
