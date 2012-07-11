Vagrant::Config.run do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "centos6_64-"

  # The url from where the 'config.vm.box' box will be fetched if it
  # doesn't already exist on the user's system.
  config.vm.box_url = "http://yum.mnxsolutions.com/vagrant/centos_56_32.box"

config.vm.customize do |vm|
  vm.memory_size = 1024
end
  # Boot with a GUI so you can see the screen. (Default is headless)
   config.vm.boot_mode = :gui

  # Assign this VM to a host only network IP, allowing you to access it
  # via the IP.
  # config.vm.network "33.33.33.10"
  #config.vm.network :hostonly, "10.10.10.2"
  config.vm.customize ["modifyvm", :id, "--rtcuseutc", "on"]
  config.ssh.max_tries = 20

  # Forward a port from the guest to the host, which allows for outside
  # computers to access the VM, whereas host only networking does not.
  #config.vm.forward_port 27030, 27030
  #config.vm.forward_port 27031, 27031

  # Share an additional folder to the guest VM. The first argument is
  # an identifier, the second is the path on the guest to mount the
  # folder, and the third is the path on the host to the actual folder.


  # Enable provisioning with chef solo, specifying a cookbooks path (relative
  # to this Vagrantfile), and adding some recipes and/or roles.
  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = "cookbooks"
    chef.roles_path = 'roles'

    chef.add_role "oracle-server"

    chef.node_name="vagrant_oracle"

    #chef.json ={
    #
    #    "wordpress" => {
    #        "db" => {
    #            "database" => "wordpress",
    #            "user" => "wordpress",
    #            "password" => "wordpress"
    #        }
    #    }
    #}
  end
end
