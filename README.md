# Vagrant_IOS_Luytens_Wouter
 When trying to connect to cisco switchen using ssh make sure to execute the following command:

 echo "KexAlgorithms diffie-hellman-group-exchange-sha1,diffie-hellman-group14-sha1" >> /etc/ssh/ssh_config

Initial ssh config must be done on switches before executing 

add the following in /etc/ansible/hosts
[switches]
Router1 ansible_host=192.168.171.x num=1
Router2 ansible_host=192.168.171.x num=2

[switches:vars]
ansible_become=yes
ansible_become_method=enable
ansible_become_password=<"password from switch/router">
ansible_network_os=ios
ansible_user=<"username from switch/router">
ansible_password=<"password from switch/router">

and add in /etc/ansible/ansible.cfg
host_key_checking = False