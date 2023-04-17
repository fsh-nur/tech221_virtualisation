# How to provision in vagrant


### Create a shell script
1. Create a shell script in your local host called provision.sh

2. Input the shebang:
`#!/bin/bash`

3. Input the following script:
```
sudo apt update -y # update the system 
sudo apt upgrade -y # upgrade the system
sudo apt install nginx -y # install the nginx web server 
sudo systemctl restart nginx # enable the web server
sudo systemctl enable nginx
```
### Alter the Vagrantfile

1. Add the following code to the vagrant file:
`  config.vm.provision "shell", path: "provision.sh"
`
2. Your vagrant file should show the following code:
```
Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"
  config.vm.network "private_network", ip: "192.168.10.100"
  config.vm.provision "shell", path: "provision.sh"


end 
```
3. Use the following command in the terminal:

```
vagrant up
```
4. You should see the following page when inputting the IP address in the vagrant file:

