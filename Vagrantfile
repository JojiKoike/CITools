# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANT_API_VERSION="2"
Vagrant.configure(VAGRANT_API_VERSION) do |config|

  ################################################
  # Section 1 : Common Settings
  ################################################
  if Vagrant.has_plugin?("vagrant-cachier")
    config.cache.scope = :box
  end

  ########################################################
  # Section 2 : Machine Settings
  ########################################################
  # CITools Server (Jenkins and SonarQube All in One)
  config.vm.define :citools do |citools|
    # Base Box
    citools.vm.box = "bento/ubuntu-16.04"
    # SSH Key
    citools.ssh.insert_key = false
    # Port Forwarding Configuration
    #citools.vm.network "forwarded_port", guest: 8080, host:8081
    #citools.vm.network "forwarded_port", guest: 9000, host:8082
    citools.vm.network "private_network", ip: "192.168.33.200"
    # VM Hardware Spec Customize
    citools.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "8192", "--cpus", "2", "--ioapic", "on"]
    end
  end

  ########################################################
  # Section 3 : Provisionning
  ########################################################
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "provisioning/site.yml"
    ansible.groups = {
      "citools_servers" => ["citools"]
    }
  end
 end
