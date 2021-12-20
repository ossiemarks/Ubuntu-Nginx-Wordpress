Vagrant.configure(2) do |config|
	config.vm.box = "generic/ubuntu2004"
	config.vm.provider "virtualbox" do |vb|
    vb.gui = false
		vb.memory = "1024"
    #vb.cpu = "1"
  end
  config.vm.synced_folder ".", "/vagrant"
  config.vm.define "wp" do |wp|
    wp.vm.hostname = "wp"
    wp.vm.network  "private_network", ip: "172.20.20.33"
    wp.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "front.yml"
      ansible.limit = "all"
    end
    
  end

    
end