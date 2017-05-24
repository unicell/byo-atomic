Vagrant.configure(2) do |config|

  config.vm.box = "fedora/24-cloud-base"

  config.vm.provider "virtualbox" do |vb, override|
    vb.cpus = 8
    vb.memory = 8192
  end

  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.provision "file", source: "byo-atomic.sh", destination: "byo-atomic.sh"
  config.vm.provision "shell",
    inline: "sed -i 's#^working_dir=.*#working_dir=\"/home/vagrant/working\"#g' byo-atomic.sh"

end
