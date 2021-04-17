Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"
  config.vm.provider :virtualbox do |v|
    v.memory = 512
    v.linked_clone = true
  end

  config.vm.define "monitor" do |monitor|
    monitor.vm.hostname = "monitor"
    monitor.vm.network :private_network, ip: "192.168.60.2"
  end

  config.vm.define "k8smaster" do |k8smaster|
    k8smaster.vm.hostname = "k8smaster"
    k8smaster.vm.network :private_network, ip: "192.168.60.3"
  end

  config.vm.define "k8spod1" do |k8spod1|
    k8spod1.vm.hostname = "k8spod1"
    k8spod1.vm.network :private_network, ip: "192.168.60.4"
  end

  config.vm.define "k8spod2" do |k8spod2|
    k8spod2.vm.hostname = "k8spod2"
    k8spod2.vm.network :private_network, ip: "192.168.60.5"
  end

  config.vm.define "k8spod3" do |k8spod3|
    k8spod3.vm.hostname = "k8spod3"
    k8spod3.vm.network :private_network, ip: "192.168.60.6"
  end

  config.vm.define "db" do |db|
    db.vm.hostname = "db"
    db.vm.network :private_network, ip: "192.168.60.7"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "check.yml"
    ansible.groups = {
      "monitoring" => ["monitor"],
      "k8smaster" => ["k8smaster"],
      "k8spods" => ["k8spod1", "k8spod2", "k8spod3"]
    }
  end
end
