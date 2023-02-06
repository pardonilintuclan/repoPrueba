Vagrant.configure("2") do |config|
 if Vagrant.has_plugin? "vagrant-vbguest"
 config.vbguest.no_install = true
 config.vbguest.auto_update = false
 config.vbguest.no_remote = true
 end
 config.vm.define :cliente do |cliente|
 cliente.vm.box = "centos/stream8"
 cliente.vm.network :private_network, ip: "192.168.50.2"
 cliente.vm.network "forwarded_port", guest: 5080, host: 8080
 cliente.vm.hostname = "cliente"
 cliente.vm.synced_folder ".", "/vagrant", type: "rsync"
 end
 config.vm.define :servidor do |servidor|
 servidor.vm.box = "centos/stream8"
 servidor.vm.network :private_network, ip: "192.168.50.3"
 servidor.vm.hostname = "servidor"
 end
end