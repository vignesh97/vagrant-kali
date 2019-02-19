
Vagrant.configure("2") do |config|

  config.vm.define "kali" do |kali_conf|
    kali_conf.vm.box = "tonijaaskelainen/kali" # This is a Kali Linux Light 2017.2 64-bit base box with PostgreSQL and Metasploit Framework

    kali_conf.vm.provider "virtualbox" do |vb|
      vb.name = "Kali-Linux-Light-2017.2-amd64"
      #vb.gui = true
      #vb.customize ["modifyvm", :id, "--FLAG", "VALUE"]
    end

    kali_conf.vm.base_mac = "080027D7153E"
    #kali_conf.vm.network "private_network", ip: "192.168.56.102" # This did not work

    kali_conf.ssh.username = "root"
    kali_conf.ssh.password = "toor"

    kali_conf.vm.provision "shell", inline: $install # You can comment this out if you do not want to install normal Kali Linux tools
  end

  config.vm.define "ms2" do |ms2_conf|
    ms2_conf.vm.box = "tonijaaskelainen/ms2" # This is Metasploitable 2 with VirtualBox 5.1.30 Guest Additions and passwordless sudo and root

    ms2_conf.vm.provider "virtualbox" do |vb|
      vb.name = "Metasploitable-2"
      #vb.customize ["modifyvm", :id, "--FLAG", "VALUE"]
    end

    ms2_conf.vm.base_mac = "080027362690"
    ms2_conf.vm.network "private_network", ip: "192.168.56.101" # This is a Host-only network

    ms2_conf.ssh.username = "msfadmin"
    ms2_conf.ssh.password = "msfadmin"
  end

end

