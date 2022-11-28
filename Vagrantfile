#  -*-  mode:  ruby -*-
# vi: set ft=ruby  :

VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION)  do  |config|
  # General Vagrant VM   configuration.
  config.vm.box  =  "centos/7"
  config.ssh.insert_key  =  false
  config.vm.synced_folder  ".",  "/vagrant",  disabled:  true

  #  ControlMaster
  config.vm.define  "master"  do  |app|
    app.vm.hostname  =  "master.dev"
    #app.vm.provider  :virtualbox  do  |v|
    #    v.memory  =  4092
    #end
    app.vm.network  :private_network,  ip:  "192.168.60.100"
  end

    #  Application  server 1.
    config.vm.define  "app1"  do  |app|
    app.vm.hostname  =  "app1.dev"
    app.vm.network  :private_network,  ip:  "192.168.60.4"
    end

    #  Application  server 2.
    config.vm.define  "app2"  do  |app|
    app.vm.hostname  =  "app2.dev"
    app.vm.network  :private_network,  ip:  "192.168.60.5"
    end

    #  Database  server.
    config.vm.define  "db"  do  |db|
    db.vm.box  =  "ubuntu/focal64"
    db.vm.hostname  =  "db.dev"
    db.vm.network  :private_network,  ip:  "192.168.60.6"
    end
end
