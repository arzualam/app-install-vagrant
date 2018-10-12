
Vagrant.configure("2") do |config|


  config.vm.define "devtest" do |subconfig|
    subconfig.vm.box = "ubuntu/xenial64"
    subconfig.vm.hostname= "devtest"
    subconfig.vm.provider "devtest" do |v|
      v.customize ["modifyvm" , :id, "--cpuexecutioncap", "30"]
    end
    subconfig.vm.network:private_network, ip: "10.10.10.20"
    subconfig.vm.network "forwarded_port", guest: 80, host: 1234
    subconfig.vm.provision "ansible" do |ansible|
     ansible.playbook = "/home/ubuntu/vagrant/haproxy/playbook.yml"
    end
  end

end
