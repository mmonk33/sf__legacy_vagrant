$script = <<SCRIPT
 sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
 wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
 apt-get update && export DEBIAN_FRONTEND="noninteractive" && apt-get install postgresql-8.4 -y
SCRIPT

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
  config.vm.provision "shell", inline: $script
end