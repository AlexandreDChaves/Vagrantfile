machines = {
  "node01" => {"memory" => "512", "cpu" => "1", "image" => "gusztavvargadr/windows-11"},
  "node02" => {"memory" => "512", "cpu" => "1", "image" => "gusztavvargadr/windows-11"},
  "node03" => {"memory" => "512", "cpu" => "1", "image" => "gusztavvargadr/windows-11"},
  "node04" => {"memory" => "512", "cpu" => "1", "image" => "gusztavvargadr/windows-11"}
}

Vagrant.configure("2") do |config|

  machines.each do |name, conf|
    config.vm.define "#{name}" do |machine|
      machine.vm.box = "#{conf["image"]}"
      machine.vm.hostname = "#{name}"
      machine.vm.network "public_network"
      machine.vm.provider "virtualbox" do |vb|
        vb.name = "#{name}"
        vb.memory = conf["memory"]
        vb.cpus = conf["cpu"]
        
      end
      machine.vm.provision "shell", path: "instalar-docker.sh"   
    end
  end
end
#Acessando a máquina virtual: vagrant ssh node01
#docker swarm --advertise--addr + IP