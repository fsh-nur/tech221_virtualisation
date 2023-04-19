## How to run a process in the background in linux

A background process is a process/command that is started from a terminal and runs in the background, without interaction from the user.
1. To run a command in the background, add the ampersand symbol (&) at the end of the command:

``` <command> & ```



## How to run nodejs app as background process using pm2

#### PM2 Runtime is a Production Process Manager for Node.js applications with a built-in Load Balancer. It allows you to keep applications alive forever, to reload them without downtime and facilitate common Devops tasks.

- You have already run `vagrant up` and `vagrant ssh` into your app VM
- Firstly, make sure you have the latest version of node
1. Install the node ppa 
```
curl -sL https://deb.nodesource.com/setup_16.x -o /tmp/nodesource_setup.sh
```
2. You may inspect the contents of the downloaded script using:
```
nano /tmp/nodesource_setup.sh
```
3. Once you are happy with this, exit your editor
` CTR + X`
4. Run this command
```
sudo bash /tmp/nodesource_setup.sh
```
5. Install Nodejs
```
sudo apt install nodejs
```
6. You can check the version with this command
```
node -v
```
7. You should get the output `v16.19.0`
8. Now navigate to the app directory
```
cd app
```
9. Use pm2 to run the process in the background with this command:
```
pm2 start app.js
```
10. You can see the app is online and in the background here:
![pm2](https://user-images.githubusercontent.com/129324316/233121137-bb3430c4-83ce-4e06-a5f2-41762a5ec6e6.png)

