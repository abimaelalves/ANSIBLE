$samplescript = <<SCRIPT
yum update -y && yum install net-tools -y
sudo useradd ansibot;
echo ansibot:PMOasmoasdfQWEasd1231231231 | chpasswd; 
echo "ansibot ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers
id ansibot;
ls -l /home;
sed -i 's|[#]*PasswordAuthentication no|PasswordAuthentication yes|g' /etc/ssh/sshd_config;
systemctl restart sshd;
SCRIPT

Vagrant.configure("2") do |config|
  config.vm.define "master" do |subconfig|
    subconfig.vm.box = "centos/7"
    subconfig.vm.hostname = "master.local"
    subconfig.vm.provision "shell", inline: $samplescript
    subconfig.vm.network "public_network", bridge: "wlp9s0"
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.cpus = "1"
    end
  end
end
#
#  config.vm.define "node1" do |subconfig|
#    subconfig.vm.box = "centos/7"
#    subconfig.vm.hostname = "node1"
#    subconfig.vm.provision "shell", inline: $samplescript
#    subconfig.vm.network "private_network", ip: "192.168.50.11"
#    config.vm.provider "virtualbox" do |vb|            UIOGiaugasd!@#!@
#      vb.memory = "512"
#      vb.cpus = "1"
#    end
#  end
#
#  config.vm.define "node2" do |subconfig|
#    subconfig.vm.box = "centos/7"
#    subconfig.vm.hostname = "node2"
#    subconfig.vm.provision "shell", inline: $samplescript
#    subconfig.vm.network "private_network", ip: "192.168.50.12"
#    config.vm.provider "virtualbox" do |vb|
#      vb.memory = "512"
#      vb.cpus = "1"
#    end
#  end
#end