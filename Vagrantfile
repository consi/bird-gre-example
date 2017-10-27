# Declare how many bird machines do we want
N=5
Vagrant.configure("2") do |config|    
    (1..N).each do |machine_id|
        config.vm.define "bird#{machine_id}" do |machine|
            #Make instances more comact
            machine.vm.provider :virtualbox do |vbox|
                # Let's name machines in human way
                vbox.name = "vm_bird_#{machine_id}"
                vbox.customize ["modifyvm", :id, "--memory", 254]
                vbox.customize ["modifyvm", :id, "--cpus", 1]
            end
            #With debian jessie
            machine.vm.box = "debian/jessie64"
            machine.ssh.insert_key = false
            #Hostname birdN
            machine.vm.hostname = "bird#{machine_id}"
            #With IPs assigned one-by-one
            machine.vm.network "private_network", ip: "192.168.42.#{10+machine_id}"
            #And execute ansible when all of this will be done.
            if machine_id == N
                # Install some ansible deps and ansible itself
                machine.vm.provision "shell", inline: "sudo apt-get install -y python-pip python-dev"
                machine.vm.provision "shell", inline: "sudo pip install -U pip"
                machine.vm.provision "shell", inline: "sudo pip install -U setuptools"
                machine.vm.provision "shell", inline: "sudo pip install ansible"
                machine.vm.provision :ansible do |ansible|
                    ansible.limit = "all"
                    ansible.playbook = "bird.yml"
                end
            end
        end
    end
end