# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|
  config.vm.define "leaf1" do |leaf1|
        leaf1.vm.box = "n9k"
        leaf1.ssh.insert_key = false
        leaf1.vm.boot_timeout = 180
        leaf1.vm.synced_folder '.', '/vagrant', disabled: true
        leaf1.vm.network :forwarded_port, guest: 80, host: 8881, id: 'http'
        leaf1.vm.network "private_network", auto_config: false, virtualbox__intnet: "vtepA_spine"
        leaf1.vm.network "private_network", auto_config: false, virtualbox__intnet: "vtepA_router1"
        leaf1.vm.provider :virtualbox do |vb|
                vb.name = "leaf1"
                vb.customize ['modifyvm',:id,'--memory','6144']
                vb.customize ['modifyvm',:id,'--macaddress1','0800276CEEAA']
                vb.customize ['modifyvm',:id,'--nicpromisc2','allow-all']
                vb.customize ['modifyvm',:id,'--nicpromisc3','allow-all']
                vb.customize ['modifyvm',:id,'--nicpromisc4','allow-all']
                vb.customize ['modifyvm',:id,'--uart1','0x3F8','4']
                vb.customize ['modifyvm',:id,'--uartmode1','server','/tmp/leaf1']
                vb.customize "pre-boot", [
                        "storageattach", :id,
                        "--storagectl", "SATA",
                        "--port", "1",
                        "--device", "0",
                        "--type", "dvddrive",
                        "--medium", "./leaf1_config.iso",
                ]
        end
  end
  config.vm.define "leaf2" do |leaf2|
        leaf2.vm.box = "n9k"
        leaf2.ssh.insert_key = false
        leaf2.vm.boot_timeout = 180
        leaf2.vm.synced_folder '.', '/vagrant', disabled: true
        leaf2.vm.network :forwarded_port, guest: 80, host: 8882, id: 'http'
        leaf2.vm.network "private_network", auto_config: false, virtualbox__intnet: "vtepB_spine"
        leaf2.vm.network "private_network", auto_config: false, virtualbox__intnet: "vtepB_router2"
        leaf2.vm.provider :virtualbox do |vb|
                vb.name = "leaf2"
                vb.customize ['modifyvm',:id,'--memory','6144']
                vb.customize ['modifyvm',:id,'--macaddress1','0800276CEEBB']
                vb.customize ['modifyvm',:id,'--nicpromisc2','allow-all']
                vb.customize ['modifyvm',:id,'--nicpromisc3','allow-all']
                vb.customize ['modifyvm',:id,'--nicpromisc4','allow-all']
                vb.customize ['modifyvm',:id,'--uart1','0x3F8','4']
                vb.customize ['modifyvm',:id,'--uartmode1','server','/tmp/leaf2']
                vb.customize "pre-boot", [
                        "storageattach", :id,
                        "--storagectl", "SATA",
                        "--port", "1",
                        "--device", "0",
                        "--type", "dvddrive",
                        "--medium", "./leaf2_config.iso",
                ]
        end
  end
  config.vm.define "spine1" do |spine1|
        spine1.vm.box = "n9k"
        spine1.ssh.insert_key = false
        spine1.vm.boot_timeout = 180
        spine1.vm.synced_folder '.', '/vagrant', disabled: true
        spine1.vm.network :forwarded_port, guest: 80, host: 8883, id: 'http'
        spine1.vm.network "private_network", auto_config: false, virtualbox__intnet: "vtepA_spine"
        spine1.vm.network "private_network", auto_config: false, virtualbox__intnet: "vtepB_router2"
        spine1.vm.provider :virtualbox do |vb|
                vb.name = "spine1"
                vb.customize ['modifyvm',:id,'--memory','6144']
                vb.customize ['modifyvm',:id,'--macaddress1','0800276CEECC']
                vb.customize ['modifyvm',:id,'--nicpromisc2','allow-all']
                vb.customize ['modifyvm',:id,'--nicpromisc3','allow-all']
                vb.customize ['modifyvm',:id,'--nicpromisc4','allow-all']
                vb.customize ['modifyvm',:id,'--uart1','0x3F8','4']
                vb.customize ['modifyvm',:id,'--uartmode1','server','/tmp/spine1']
                vb.customize "pre-boot", [
                        "storageattach", :id,
                        "--storagectl", "SATA",
                        "--port", "1",
                        "--device", "0",
                        "--type", "dvddrive",
                        "--medium", "./spine1_config.iso",
                ]
        end
  end
  config.vm.define "spine2" do |spine2|
        spine2.vm.box = "n9k"
        spine2.ssh.insert_key = false
        spine2.vm.boot_timeout = 180
        spine2.vm.synced_folder '.', '/vagrant', disabled: true
        spine2.vm.network :forwarded_port, guest: 80, host: 8884, id: 'http'
        spine2.vm.network "private_network", auto_config: false, virtualbox__intnet: "vtepA_router1"
        spine2.vm.network "private_network", auto_config: false, virtualbox__intnet: "vtepB_spine"
        spine2.vm.provider :virtualbox do |vb|
                vb.name = "spine2"
                vb.customize ['modifyvm',:id,'--memory','6144']
                vb.customize ['modifyvm',:id,'--macaddress1','0800276CEEDD']
                vb.customize ['modifyvm',:id,'--nicpromisc2','allow-all']
                vb.customize ['modifyvm',:id,'--nicpromisc3','allow-all']
                vb.customize ['modifyvm',:id,'--nicpromisc4','allow-all']
                vb.customize ['modifyvm',:id,'--uart1','0x3F8','4']
                vb.customize ['modifyvm',:id,'--uartmode1','server','/tmp/spine2']
                vb.customize "pre-boot", [
                        "storageattach", :id,
                        "--storagectl", "SATA",
                        "--port", "1",
                        "--device", "0",
                        "--type", "dvddrive",
                        "--medium", "./spine2_config.iso",
                ]
        end
  end

end
  
