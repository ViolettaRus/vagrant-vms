Vagrant.configure("2") do |config|
  # Общая конфигурация для всех ВМ
  config.vm.box = "bento/centos-stream-9"
  config.vm.synced_folder "./shared", "/vagrant_shared", type: "virtualbox"

  # ВМ 1
  config.vm.define "vm1" do |vm1|
    vm1.vm.hostname = "centos-vm1"
    vm1.vm.network "public_network", bridge: "en0: Wi-Fi"
    
    # Провизионирование - копирование файла
    vm1.vm.provision "file", source: "./provision/file_to_copy.txt", destination: "/home/vagrant/copied_file.txt"
  end

  # ВМ 2
  config.vm.define "vm2" do |vm2|
    vm2.vm.hostname = "centos-vm2"
    vm2.vm.network "public_network", bridge: "en0: Wi-Fi"
    
    # Провизионирование - копирование файла
    vm2.vm.provision "file", source: "./provision/file_to_copy.txt", destination: "/home/vagrant/copied_file.txt"
  end
end