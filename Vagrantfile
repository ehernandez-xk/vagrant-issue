# Don't touch unless you know what you're doing!
# Use host.yaml to manage the local environment options for this project

require 'yaml'

host_sync_folder = "/vagrant"

Vagrant.configure("2") do |config|
  # The docker host VM
  config.vm.box_version = "1.12.2"
  config.vm.box = "xk_test/boot2docker-example"
  config.vm.define "dockerhost"

  #mount directory
  config.vm.synced_folder ".", host_sync_folder, type: "nfs", mount_options: ["nolock", "vers=3", "udp"], id: "nfs-sync"

  #provision xxx directory
  config.vm.provision "shell", inline: "mkdir /xxx"

  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--memory", "3072"]
  end
end
