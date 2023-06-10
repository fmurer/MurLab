Vagrant.configure("2") do |config|

    config.vm.define "VELOCIRAPTOR" do |cfg|
        cfg.vm.box = "ubuntu/focal64"
        cfg.vm.hostname = "velociraptor.murlab.local"
        cfg.vm.network "private_network", ip: "192.168.56.6", gateway: "192.168.56.1", dns: "9.9.9.9"

        cfg.vm.provider "virtualbox" do |vb, override|
            vb.gui = false
            vb.name = "velociraptor.murlab.local"
            vb.customize ["modifyvm", :id, "--memory", 4096]
            vb.customize ["modifyvm", :id, "--cpus", 2]
            vb.customize ["modifyvm", :id, "--vram", "32"]
            vb.customize ["modifyvm", :id, "--nicpromisc2", "allow-all"]
            vb.customize ["modifyvm", :id, "--clipboard", "bidirectional"]
            vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
            vb.customize ["modifyvm", :id, "--uartmode1", "disconnected" ]
            vb.customize ["setextradata", "global", "GUI/SuppressMessages", "all" ]
        end

        cfg.vm.provision "ansible" do |ansible|
            ansible.verbose = "v"
            ansible.playbook = "ansible/velociraptor_playbook.yaml"
        end
    end
end