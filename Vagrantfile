# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "centos/7"
  config.vm.synced_folder ".",
    "/vagrant",
    type: "nfs",
    nfs_udp: false

  config.vm.provider :libvirt do |libvirt|
    libvirt.cpus = 2
    libvirt.memory = 4096
    libvirt.nested = true
    libvirt.graphics_type = 'spice'
    libvirt.video_type = 'virtio'
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook-setup-docker.yaml"
  end
end
