VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "centos"

  config.vm.define :leansw do |lean|
    lean.vm.hostname = "leansw"

    lean.vm.network :forwarded_port, guest: 8080, host: 8080
    lean.vm.network :forwarded_port, guest: 8088, host: 8088
    lean.vm.network :forwarded_port, guest: 29418 , host: 29418

    lean.vm.network "private_network", ip: "192.168.1.111"
    lean.vm.network "private_network", ip: "10.17.3.111"
    # lean.vm.network "public_network"
  end

  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--memory", 2048]
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "./gerrit.yml"
    ansible.inventory_path = "./hosts"
    ansible.sudo = true
    # debug is on
    ansible.verbose = "vvvv"
  end

  end
