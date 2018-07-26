Vagrant.configure("2") do |config|

  # Testing different boxes
  config.vm.define "stretch" do |subconfig|
    subconfig.vm.box = "debian/stretch64"
    subconfig.vm.network "forwarded_port", guest: 443, host: 8443
    subconfig.vm.network "forwarded_port", guest: 80, host: 8080
  end

  #config.vm.define "xenial" do |subconfig|
  #  subconfig.vm.box = "ubuntu/xenial64"
  #end

  #config.vm.define "bionic" do |subconfig|
  #  subconfig.vm.box = "ubuntu/bionic64"
  #end

  # Provisionning
  config.vm.provision "shell", inline: "echo hello \
  && apt update \
  && apt install vim less ansible python-dnspython -y \
  && cd /vagrant/playbook \
  && ansible-playbook -i ../inventory/hosts monarc.yaml"

end

# vi:syntax=ruby
