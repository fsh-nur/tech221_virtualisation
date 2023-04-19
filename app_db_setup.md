# Setting up 2 virtual machines using vagrant: app and db

## Prerequisites include:
- **app** folder
- **environment** folder
- delete the launch of the app in the shellscript

## Modifying the Vagrant File, to create an "app" vm and a "db" vm
1. Rename default vm to "app"

```
config.vm.define "app" do |app|
```

2. Make sure to indent all of the config files, and change "config" to "app"
3. Close this VM configuration
```
end
```
4. Now create your db virtual machine
```
config.vm.define "db" do |db|

```
5. Set up linux command
```
db.vm.box = "ubuntu/xenial64"

```
6. Set up your IP
```
db.vm.network "private_network", ip: "192.168.10.150"

```
7. Make sure to `end` this vm configuration.
8. Your vagrant file should look like this 
![vagrant file setup](https://user-images.githubusercontent.com/129324316/233061258-e3751b0d-f799-4f16-99e4-d445a2bea13a.png)
9. Create the virtual machines
```
vagrant up
```
10. In order to ssh into both the app and the dp you must open GitBash (as admin) and use the following command:
11. Navigate to the vagrant directory containing the virtual machines
12. Vagrant SSH into app
```
vagrant ssh app
```
13. Open another GitBash terminal (as admin) and vagrant ssh into db
```
vagrant ssh db
```
## Download MongoDB in our system

14. Update the system in the db GitBash
```
sudo apt update -y
```
15. Upgrade the system in the db GitBash
```
sudo apt upgrade -y
```
16. Get the MongoDB key and import MongoDB key
```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv D68FA50FEA312927
```
17. Obtain the MongoDB key in order to download our specific MongoDB on the web
```
echo "deb https://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list
```
18. Update the system in order to grab all mongoDB packages
```
sudo apt update -y
```
19. Upgrade the system in order to obtain all mongoDB packages
```
sudo apt upgrade -y
```
20. Now we download MongoDB 
```
sudo apt-get install -y mongodb-org=3.2.20 mongodb-org-server=3.2.20 mongodb-org-shell=3.2.20 mongodb-org-mongos=3.2.20 mongodb-org-tools=3.2.20
```
21. Start MongoDB 
```
sudo systemctl start mongod
```
22. Check the status to see if it is running properly
```
sudo systemctl status mongod
```
23. If everything is well you should see this in GitBash:

![mongodb correct](https://user-images.githubusercontent.com/129324316/233082455-1b5dd56c-2d82-45ac-ac91-43b7a0a921a4.png)

