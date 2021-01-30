IMAGE_NAME = "bento/ubuntu-18.04"

Vagrant.configure("2") do |config|
    config.ssh.insert_key = false
    config.vm.provider "virtualbox" do |v|
        v.memory = 2048
        v.cpus = 2
    end
    config.vm.define "ElaRedis" do |master|
		master.vm.box = IMAGE_NAME
        master.vm.network "private_network", ip: "172.28.128.8"
        master.vm.hostname = "ElaHost"
		master.vm .provision "ansible_local" do |ansible|
            ansible.playbook = "dockersetup-playbook.yaml"
			ansible.version = '2.9.17'
         end
  
     end
end