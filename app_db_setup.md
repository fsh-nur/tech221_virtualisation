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

