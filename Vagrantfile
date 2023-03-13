Vagrant.configure("2") do |config|

  config.vm.box = "generic/fedora37"

  config.vm.provider :libvirt do |libvirt|
    # libvirt.management_network_mode = "none"
    libvirt.management_network_address = "192.168.121.0/24"
    libvirt.driver = "kvm"
    libvirt.uri = "qemu:///system"
    # libvirt.storage_pool_name = "dev"
    libvirt.memory = 8192
    libvirt.cpu_mode = "host-passthrough"
    libvirt.cpus = 8
    libvirt.cputopology :sockets => "1", :cores => "4", :threads => "2"
  end

  # config.vm.network "public_network", dev: "bridge0", mode: "bridge", type: "bridge"
  # config.vm.network "private_network", ip: "10.20.30.10", netmask: "255.255.255.0"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yaml"
  end
end
