Vagrant.configure("2") do |config|
  config.vm.box_version = "1.12.2"
  config.vm.box = "xk_test/boot2docker-example"

  #mount directory
  config.vm.synced_folder ".", "/vagrant", type: "nfs", mount_options: ["nolock", "vers=3", "udp"], id: "nfs-sync"

  #provision xxx directory
  config.vm.provision "shell", inline: "mkdir /xxx"

  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--memory", "3072"]
  end
end
