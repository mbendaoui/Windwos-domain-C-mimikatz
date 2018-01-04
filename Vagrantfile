# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
#Vagrant.configure(2) do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.
  $GOOGLE_PROJECT_ID = "yOUR PROJECT"
  $GOOGLE_CLIENT_EMAIL = "YOUR-EAMIL@developer.gserviceaccount.com"
  $GOOGLE_JSON_KEY_LOCATION = "YOUR-PROJECT.json"
  $LOCAL_USER = "YOUR USERNAME"
  $LOCAL_SSH_KEY = "~/.ssh/id_rsa"


Vagrant.configure("2") do |config|

  config.vm.box = "google/gce"
  config.vm.define :z1c do |z1c|
   z1c.vm.provider :google do |google, override|
     google.google_project_id = $GOOGLE_PROJECT_ID
     google.google_client_email = $GOOGLE_CLIENT_EMAIL
     google.google_json_key_location = $GOOGLE_JSON_KEY_LOCATION
     google.zone = "europe-west3-a"

     override.ssh.username = $LOCAL_USER
     override.ssh.private_key_path = $LOCAL_SSH_KEY

     google.zone_config "europe-west3-a" do |z1c_zone|
       z1c_zone.name = "win-ad2012"
       z1c_zone.image = "windows-server-2012-r2-dc-v20171114"
       z1c_zone.machine_type = "n1-standard-1"
       z1c_zone.zone = "europe-west3-a"
        z1c_zone.disk_size = "60"
    z1c_zone.external_ip = "ip-extern"
    #z1c_zone.interanl_ip = "adsrvip"
     end
   end
 end

 config.vm.define :z1f do |z1f|
   z1f.vm.provider :google do |google, override|
     google.google_project_id = $GOOGLE_PROJECT_ID
     google.google_client_email = $GOOGLE_CLIENT_EMAIL
     google.google_json_key_location = $GOOGLE_JSON_KEY_LOCATION
     google.zone = "europe-west3-a"

     override.ssh.username = $LOCAL_USER
     override.ssh.private_key_path = $LOCAL_SSH_KEY

     google.zone_config "europe-west3-a" do |z1f_zone|
       z1f_zone.name = "win-client-2008s"
       z1f_zone.image = "windows-server-2008-r2-dc-v20171114"

       z1f_zone.machine_type = "n1-standard-2"
       z1f_zone.zone = "europe-west3-a"
       z1f_zone.disk_size = "60"
     end
   end
 end

end







 































  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
 # config.vm.box = "base"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Define a Vagrant Push strategy for pushing to Atlas. Other push strategies
  # such as FTP and Heroku are also available. See the documentation at
  # https://docs.vagrantup.com/v2/push/atlas.html for more information.
  # config.push.define "atlas" do |push|
  #   push.app = "YOUR_ATLAS_USERNAME/YOUR_APPLICATION_NAME"
  # end

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   sudo apt-get update
  #   sudo apt-get install -y apache2
  # SHELL
