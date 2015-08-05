# -*- mode: ruby -*-
# vi: set ft=ruby :
#
# https://dl.bintray.com/mitchellh/consul/0.5.2_web_ui.zip

Vagrant.configure(2) do |config|

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y unzip screen
    cd /vagrant/pkg
    if [ ! -f 0.5.2_linux_amd64.zip ]; then
      wget https://dl.bintray.com/mitchellh/consul/0.5.2_linux_amd64.zip
    fi
    if [ ! -f consul ]; then
      unzip 0.5.2_linux_amd64.zip
    fi
    cp consul /usr/local/bin
  SHELL

  config.vm.define "s1" do |s1|
    s1.vm.box = "ubuntu/trusty64"
    s1.vm.hostname = "s1"
    s1.vm.network "private_network", ip: "192.168.45.11"
    s1.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.name = "consul-example-s1"
    end
    s1.vm.provision "shell", inline: <<-SHELL
    SHELL
  end

  config.vm.define "s2" do |s2|
    s2.vm.box = "ubuntu/trusty64"
    s2.vm.hostname = "s2"
    s2.vm.network "private_network", ip: "192.168.45.12"
    s2.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.name = "consul-example-s2"
    end
    s2.vm.provision "shell", inline: <<-SHELL
    SHELL
  end

  config.vm.define "s3" do |s3|
    s3.vm.box = "ubuntu/trusty64"
    s3.vm.hostname = "s3"
    s3.vm.network "private_network", ip: "192.168.45.13"
    s3.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.name = "consul-example-s3"
    end
    s3.vm.provision "shell", inline: <<-SHELL
    SHELL
  end

  config.vm.define "a1" do |a1|
    a1.vm.box = "ubuntu/trusty64"
    a1.vm.hostname = "a1"
    a1.vm.network "private_network", ip: "192.168.45.50"
    a1.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.name = "consul-example-a1"
    end
    a1.vm.provision "shell", inline: <<-SHELL
    SHELL
  end
end

