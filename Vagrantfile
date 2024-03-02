Vagrant.configure("2") do |config|
    config.vm.provider :libvirt do |libvirt|
        libvirt.memory = 1024
    end

    config.vm.define :router_fw do |router_fw|
        router_fw.vm.synced_folder ".", "/vagrant", disabled: true
        router_fw.vm.box = "debian/bookworm64"
        router_fw.vm.hostname = "router-fw"
        router_fw.vm.network :private_network,
          :libvirt__network_name => "redfw1",
          :libvirt__dhcp_enabled => false,
          :ip => "192.168.100.2",
          :netmask => "255.255.255.0",
          :libvirt__forward_mode => "veryisolated"
    end

    config.vm.define :lan do |lan|
        lan.vm.synced_folder ".", "/vagrant", disabled: true
        lan.vm.box = "debian/bookworm64"
        lan.vm.hostname = "lan"
        lan.vm.network :private_network,
          :libvirt__network_name => "redfw1",
          :libvirt__dhcp_enabled => false,
          :ip => "192.168.100.10",
          :netmask => "255.255.255.0",
          :libvirt__forward_mode => "veryisolated",
          :libvirt__nic_model => "virtio"
    end
end
