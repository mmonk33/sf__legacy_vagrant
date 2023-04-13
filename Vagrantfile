Vagrant.configure("2") do |config|
  config.vm.define "ubuntu-ff-vm"
  config.vm.box = "sf_box"
  config.vm.box_check_update = false
  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = false  
    # Customize the amount of memory on the VM:
    vb.memory = "2048"
    vb.cpus = "4"
  end
  config.vm.provision "shell", path: "pgsqlinstall.sh"
end