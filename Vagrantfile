Vagrant.configure("2") do |config|

  config.vm.define "bridge" do |bridge|
    bridge.vm.box = "ubuntu/focal64"
    bridge.vm.network "private_network", type: "dhcp", virtualbox__intnet: "vboxnet0"
    bridge.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
    end

bridge.vm.provision "shell", inline: <<-SHELL# Atualizando a lista de pacotes e instalando o tcpdump
    sudo apt-get update
    sudo apt-get install -y tcpdump
  SHELL
  end

  config.vm.define "vm1" do |vm1|
    vm1.vm.box = "ubuntu/focal64"
    vm1.vm.network "private_network", type: "dhcp", virtualbox__intnet: "vboxnet0"
    vm1.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
    end
  end

  config.vm.define "vm2" do |vm2|
    vm2.vm.box = "ubuntu/focal64"
    vm2.vm.network "private_network", type: "dhcp", virtualbox__intnet: "vboxnet0"
    vm2.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
    end
  end
end
