Vagrant.configure(2) do |config|
    config.vm.box = "ubuntu/jammy64"

     config.vm.provision "ansible" do |ansible|
           #  ansible.verbose = "vvv"
              ansible.playbook = "playbook.yml"
          #   ansible.inventory_path = "ansible_hosts"
             ansible.become = "true"
           end
        
        
         config.vm.provider "virtualbox" do |v|
           v.memory = 1024
           v.cpus = 1
         end


    config.vm.define "web" do |web|
      web.vm.network "private_network", ip: "192.168.56.10", virtualbox__intnet: "net1"
      web.vm.hostname = "web"
    end


    config.vm.define "log" do |log|
      log.vm.network "private_network", ip: "192.168.56.15", virtualbox__intnet: "net1"
      log.vm.hostname = "log"
    end


   end


