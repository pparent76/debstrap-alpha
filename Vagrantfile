Vagrant.configure("2") do |config|
  config.vm.box = "debian/jessie64"
  config.vm.network :forwarded_port, guest: 80, host: 8080

  config.vm.provider "virtualbox" do |v|
    v.name = "Own-Mailbox"
    v.memory = 256
    v.gui = true
  end

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get -y upgrade
    cd /vagrant/
    DEBIAN_FRONTEND=noninteractive ./main.sh
  SHELL
end
