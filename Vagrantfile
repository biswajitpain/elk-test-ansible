Vagrant.configure("2") do |config|
  config.vm.define "ubuntu16" do |ubuntu16|
    ubuntu16.vm.box = "ubuntu/xenial64"
    ubuntu16.vm.hostname = 'ubuntu'
    ubuntu16.vm.box_url = "ubuntu/xenial64"
    ubuntu16.vm.synced_folder "/work/gdrive/pgdds", "/share"
    ubuntu16.vm.network :private_network, ip: "192.168.56.10"

    ubuntu16.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 4096]
     # v.customize ["modifyvm", :id, "--name", "ubuntu"]
    end
  end

  config.vm.define "centos7" do |centos7|
    centos7.vm.box = "centos/7"
    centos7.vm.hostname = 'centos'
    centos7.vm.box_url = "centos/7"

    centos7.vm.network :private_network, ip: "192.168.56.11"

    centos7.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 1024]
      v.customize ["modifyvm", :id, "--name", "centos"]
    end
  end
end
