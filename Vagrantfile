# -*- mode: ruby -*-
# vi: set ft=ruby  :

machines = {
  "centos"    => {"memory" => "1536", "cpu" => "1", "ip" => "10", "image" => "centos/7"},
  "ubuntu"    => {"memory" => "2048", "cpu" => "1", "ip" => "20", "image" => "ubuntu/bionic64"}
}

Vagrant.configure("2") do |config|

  config.vm.box_check_update = false
  config.vm.boot_timeout = 600
  machines.each do |name, conf|
    config.vm.define "#{name}" do |machine|
      machine.vm.box = "#{conf["image"]}"
      machine.vm.hostname = "#{name}.flisol.example"
      machine.vm.network "private_network", ip: "192.168.33.#{conf["ip"]}"
      machine.vm.provider "virtualbox" do |vb|
        vb.name = "#{name}"
        vb.memory = conf["memory"]
        vb.cpus = conf["cpu"]
        vb.customize ["modifyvm", :id, "--groups", "/Flisol-2021"]
      end
        if "#{conf["image"]}" == "ubuntu/bionic64" or "#{conf["image"]}" == "debian/buster64"
          machine.vm.provision "shell", inline: "apt-get update ; apt-get install python -y; hostnamectl set-hostname #{name}.flisol.example"
        end
    end
  end
end

