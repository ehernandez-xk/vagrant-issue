ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'

Vagrant.configure("2") do |config|

  config.vm.define "base" do |a|
    a.vm.provider "docker" do |d|
      d.image = "alpine"
      d.name = "base"
      d.vagrant_vagrantfile = "./dockerHost/Vagrantfile"
      d.force_host_vm = true
      d.volumes = ["/vagrant:/project"]
    end
  end
end
