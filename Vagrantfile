
Vagrant.configure("2") do |config|
  config.vm.define "VMubunte" do |vmu|
	vmu.vm.box = "ubuntu/bionic64"

  # Install Apache to your machine 
  vmu.vm.provision :shell, path: "bootstrap.sh"

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  vmu.vm.network "forwarded_port", guest: 80, host: 8080

     vmu.vm.provider "virtualbox" do |vb|
	vb.name = "VMubunte"
    vb.gui = false
  # Customize the amount of memory on the VM:
    vb.memory = "2048"
   end
  
end

	config.vm.define "VMCentos" do |vmc|
	vmc.vm.box = "centos/7"

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  vmc.vm.network "forwarded_port", guest: 80, host: 1234

    vmc.vm.provider "virtualbox" do |vb|
	vb.name = "VMCentos"
    vb.gui = false
  # Customize the amount of memory on the VM:
    vb.memory = "2048"
   end
  #vmc.vm.provision "shell", inline: <<-SHELL
    # sudo yum update 
  #SHELL
end
end