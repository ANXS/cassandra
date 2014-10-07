# -*- mode: ruby -*-
# vi: set ft=ruby :

vagrant_box_ip = "192.168.33.10"

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "2creatives/centos65-x86_64-20140116"
  config.vm.box_url = "https://github.com/2creatives/vagrant-centos/releases/download/v6.5.3/centos65-x86_64-20140116.box"
  config.vm.box_download_checksum_type="sha256"
  config.vm.box_download_checksum = "84eda9c4f00c86b62509d1007d4f1cf16b86bccb3795659cb56d1ea0007c3adc"

  config.vm.define :test_system do |c|
    c.vm.network "private_network", ip: vagrant_box_ip
    c.vm.host_name = "team.test.com"
    c.vm.provider "virtualbox" do |vb|
        vb.gui = false
        vb.customize [ "modifyvm", :id, "--memory", "512"]
        vb.customize [ "modifyvm", :id, "--cpus", "1"]
        vb.name = "test_system_cassandra"
    end
  end
  config.vm.provision "ansible" do |ansible|
      ansible.playbook = "test.yml"
      ansible.limit = vagrant_box_ip
      ansible.inventory_path  = "inventory"
      #ansible.extra_vars = { }
      ansible.verbose = "v"
      ansible.raw_arguments = ["--private-key","~/.vagrant.d/insecure_private_key"]
      ansible.host_key_checking = "false"
  end
end
