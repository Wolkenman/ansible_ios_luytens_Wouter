Vagrant.configure("2") do |config|
    config.vm.define "ansible" do |ansible|
        ansible.vm.box = "generic/ubuntu2004"
        ansible.vm.network:forwarded_port, guest: 80, host: 4567
        ansible.vm.provision :shell, path: "bootstrap.sh"
        ansible.vm.provider "vmware_desktop" do |v|
            v.gui = true
            v.vmx["memsize"] = 4096
            v.vmx["numvcpus"] = 4
        end
    end
end
