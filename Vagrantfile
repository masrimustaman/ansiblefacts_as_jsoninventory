Vagrant.configure("2") do |config|
    config.vm.define "master" do |subconfig|
      subconfig.vm.box = "centos/8"
      subconfig.vm.hostname = "master.local"
      subconfig.vm.network :private_network, ip: "10.0.0.11"
      subconfig.ssh.username = 'vagrant'
      subconfig.ssh.password = 'vagrant'
      subconfig.ssh.insert_key = false
      subconfig.vm.provision "shell", inline: <<-SHELL
        sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config    
        systemctl restart sshd.service
        echo "10.0.0.11  master.local master" >> /etc/hosts
        echo "10.0.0.12  client01.local client01" >> /etc/hosts
        echo "10.0.0.13  client02.local client02" >> /etc/hosts
        echo "10.0.0.14  client03.local client03" >> /etc/hosts
      SHELL
      # subconfig.vm.synced_folder ".", "/vagrant", type: "virtualbox"

    end

    config.vm.define "client01" do |subconfig|
      subconfig.vm.box = "centos/8"
      subconfig.vm.hostname = "client01.local"
      subconfig.vm.network :private_network, ip: "10.0.0.12"
      subconfig.ssh.username = 'vagrant'
      subconfig.ssh.password = 'vagrant'
      subconfig.ssh.insert_key = false
      subconfig.vm.provision "shell", inline: <<-SHELL
        sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config    
        systemctl restart sshd.service
        echo "10.0.0.11  master.local master" >> /etc/hosts
        echo "10.0.0.12  client01.local client01" >> /etc/hosts
        echo "10.0.0.13  client02.local client02" >> /etc/hosts
        echo "10.0.0.14  client03.local client03" >> /etc/hosts
      SHELL
      # subconfig.vm.synced_folder ".", "/vagrant", type: "virtualbox"
    end
  
  
    # config.vm.define "client02" do |subconfig|
    #   subconfig.vm.box = "StefanScherer/windows_2019"
    #   subconfig.vm.hostname = "client02.local"
    #   subconfig.vm.network :private_network, ip: "10.0.0.13"
    #   subconfig.vm.synced_folder ".", "/vagrant", type: "virtualbox"
    # end

    config.vm.define "client03" do |subconfig|
      subconfig.vm.box = "centos/8"
      subconfig.vm.hostname = "client03.local"
      subconfig.vm.network :private_network, ip: "10.0.0.14"
      subconfig.ssh.username = 'vagrant'
      subconfig.ssh.password = 'vagrant'
      subconfig.ssh.insert_key = false
      subconfig.vm.provision "shell", inline: <<-SHELL
        sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config    
        systemctl restart sshd.service
        echo "10.0.0.11  master.local master" >> /etc/hosts
        echo "10.0.0.12  client01.local client01" >> /etc/hosts
        echo "10.0.0.13  client02.local client02" >> /etc/hosts
        echo "10.0.0.14  client03.local client03" >> /etc/hosts
      SHELL
      # subconfig.vm.synced_folder ".", "/vagrant", type: "virtualbox"
    end

end