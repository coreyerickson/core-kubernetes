# -*- mode: ruby -*-
# vi: set ft=ruby :
#
# Vagrantfile used for building multi machine
# developer instances.
#
# Uncomment the ssh options below if required.
# Required in some cases when packaging or repackaging
# a vagrant box file.
#
#
BOX_IMAGE = "centos-7.3"
NODE_COUNT = 3

Vagrant.configure("2") do |config|
  config.vm.define "master" do |subconfig|
  subconfig.vm.box = BOX_IMAGE
  subconfig.vm.hostname = "master"
  subconfig.vm.network :private_network, ip: "10.22.33.10"
#  subconfig.ssh.insert_key = false
#  subconfig.ssh.private_key_path = "~/.vagrant.d/insecure_private_key"
  end

(1..NODE_COUNT).each do |i|
  config.vm.define "node#{i}" do |subconfig|
  subconfig.vm.box = BOX_IMAGE
  subconfig.vm.hostname = "node#{i}"
  subconfig.vm.network :private_network, ip: "10.22.33.#{i + 10}"
#  subconfig.ssh.insert_key = false
#  subconfig.ssh.private_key_path = "~/.vagrant.d/insecure_private_key"
  end
end
