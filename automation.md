# How to provision installation and enabling in vagrant


### Create a shell script for nginx and app deployment
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
![nginx vagrant](https://user-images.githubusercontent.com/129324316/232787060-50acda80-884c-4722-879b-84e837fe9862.png)

### Automate App Deployment in Vagrant:
Add to our shell script the following commands:
1. Install python software properties `sudo apt-get install python-software-properties`
2. Get the set-up file for version 6 of Nodejs `curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -`
3. Install node.js `sudo apt-get install nodejs -y`
4. Install process manager `sudo npm install pm2 -g`
5. Navigate to the /app directory `cd /home/vagrant/app`
8. Then install packages `sudo npm install`
9. Go to your app directory `cd app`
10. Install packages ` npm install`
11. Finally, run the app `node app.js`

How your shellscript should look:
![provisonsh](https://user-images.githubusercontent.com/129324316/232831463-26d730a7-d6e0-43b4-8330-94fdb9f0aab5.png)

10. Input `vagrant up` in terminal in VSCode
11. Input `vagrant ssh` in GitBash
14. You should see this when inputting IP address into web browser:

![sparta test app](https://user-images.githubusercontent.com/129324316/232808671-e59e08f5-718a-4716-967d-6b106b114145.png)

### Automating MongoDB download

#### Make sure you vagrant destroy in case there are other VMs running

1. Create a seperate provision.sh file in the environment directory
2. Modify the vagrant file y adding a path to this provision file
```
    db.vm.provision "shell", path: "./environment/provision.sh"

```
3. Input the shebang in the provision file
```
#!/bin/bash
```
4. Update the system 
```
sudo apt update -y
```
4. Upgrade the system
```
sudo apt upgrade -y

```
5. Input the key and `echo` the key out which contains the url where MongoDB packages will be obtained
```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv D68FA50FEA312927

echo "deb https://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list

```
6. Update and Upgrade again, this time with the keys obtained
```
sudo apt update -y
sudo apt upgrade -y
```
7. Now install MongoDB in our VM machine
```
sudo apt-get install -y mongodb-org=3.2.20 mongodb-org-server=3.2.20 mongodb-org-shell=3.2.20 mongodb-org-mongos=3.2.20 mongodb-org-tools=3.2.20

```
8. Now we start MongoDB
```
sudo systemctl start mongod

```
9. Our provision.sh should look like this

![provison sh mongodb](https://user-images.githubusercontent.com/129324316/233090929-f0b1fc5f-fb69-4a01-85e6-388bf822f70b.png)

10. Now we start our virtual machine
```
vagrant up db
```
11. We ssh into our db vm

```
vagrant ssh db
```
12. And we check the status to see if MongoDB is running on automation
```
sudo systemctl status mongod

```
13. You should see this as the output if your automation was successful

![mongodb automation](https://user-images.githubusercontent.com/129324316/233090590-a212db04-dcc0-4b8a-ae84-95b27dead429.png)

