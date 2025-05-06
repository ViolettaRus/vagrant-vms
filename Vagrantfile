Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  
  # Настройка первой ВМ
  config.vm.define "vm1" do |vm1|
    vm1.vm.hostname = "centos-vm1"
    vm1.vm.network "private_network", ip: "192.168.56.10"
    
    # Настройка общей папки через NFS
    vm1.vm.synced_folder "./shared", "/vagrant_shared", type: "nfs"
    
    # Провизионирование - копирование файла
    vm1.vm.provision "file", source: "./example.txt", destination: "/home/vagrant/example.txt"
  end

  # Настройка второй ВМ
  config.vm.define "vm2" do |vm2|
    vm2.vm.hostname = "centos-vm2"
    vm2.vm.network "private_network", ip: "192.168.56.20"
    
    # Настройка общей папки через NFS
    vm2.vm.synced_folder "./shared", "/vagrant_shared", type: "nfs"
    
    # Провизионирование - копирование файла
    vm2.vm.provision "file", source: "./example.txt", destination: "/home/vagrant/example.txt"
  end
end