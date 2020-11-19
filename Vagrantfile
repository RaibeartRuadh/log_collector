# -*- mode: ruby -*-
# vi: set ft=ruby :


WEBSERVER_IP = "192.168.10.10"
LOGSERVER_IP = "192.168.10.11"
ELKSERVER_IP = "192.168.10.12"

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"

  config.vm.define "webserver" do |webserver|
    webserver.vm.hostname = "webserver"
    webserver.vm.network "private_network", ip: WEBSERVER_IP
    webserver.vm.provision "ansible" do |ansible|
      ansible.playbook = "webserver/site.yml"
    end
  end

  config.vm.define "logserver" do |logserver|
    logserver.vm.hostname = "logserver"
    logserver.vm.network "private_network", ip: LOGSERVER_IP
    logserver.vm.provision "ansible" do |ansible|
	logserver.vm.provider "virtualbox" do |v|
      v.memory = 4096
      v.cpus = 2
       end
      ansible.playbook = "logserver/site.yml"
    end
  end
  
    config.vm.define "elkserver" do |elkserver|
    elkserver.vm.hostname = "elkserver"
    elkserver.vm.network "private_network", ip: ELKSERVER_IP
    elkserver.vm.provision "ansible" do |ansible|
	elkserver.vm.provider "virtualbox" do |v|
      v.memory = 4096
      v.cpus = 2
       end
      ansible.playbook = "elkserver/site.yml"
    end
  end

#  config.vm.provision "ELK", type:'ansible' do |ansible|
#    ansible.inventory_path = 'ansible/all.yml'
#    ansible.playbook = 'ansible/logging.yml'
#  end
 
end



#Vagrant.configure(2) do |config|
#  config.vm.box = "centos/7"
#  config.vbguest.auto_update = false#

  #config.vm.define "web" do |web|
#    web.vm.network "private_network", ip: "192.168.10.10"
#    web.vm.provider "virtualbox" do |v|
#      v.memory = 512
#      v.cpus = 1
#    end
#    web.vm.hostname = "web"
#  end

#  config.vm.define "log" do |log|
 #   log.vm.network "private_network", ip: "192.168.10.20"
 #   log.vm.provider "virtualbox" do |v|
 #     v.memory = 512
 #     v.cpus = 1
 #   end
 #   log.vm.hostname = "log"
#  end

 # config.vm.define "elk" do |elk|
 #   elk.vm.network "private_network", ip: "192.168.10.30"
 #   elk.vm.provider "virtualbox" do |v|
  #    v.memory = 4096
  #    v.cpus = 2
  #  end
  ##  elk.vm.hostname = "elk"
 # end

 # config.vm.provision "ELK", type:'ansible' do |ansible|
 #   ansible.inventory_path = './inventories/all.yml'
#    ansible.playbook = './logging.yml'
#  end
#end