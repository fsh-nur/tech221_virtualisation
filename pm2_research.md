## How to run a process in the background in linux

A background process is a process/command that is started from a terminal and runs in the background, without interaction from the user.
- You have already run `vagrant up` and `vagrant ssh` into your app VM

1. Navigate to the app folder
2. Launch your node app in the background using the ampersand at the end.
```
node app.js &
```
3.You can also see the processes that are running in the background
```
jobs
```

![jobs](https://user-images.githubusercontent.com/129324316/233310684-20a5f2f7-a38c-4d7b-896c-727c0b15d43e.png)



## How to run nodejs app as background process using pm2

#### PM2 Runtime is a Production Process Manager for Node.js applications with a built-in Load Balancer. It allows you to keep applications alive forever, to reload them without downtime and facilitate common Devops tasks.

- You have already run `vagrant up` and `vagrant ssh` into your app VM
- Firstly, make sure you have the latest version of node
1. Install the node ppa 
```
curl -sL https://deb.nodesource.com/setup_16.x -o /tmp/nodesource_setup.sh
```
2. Install Nodejs
```
sudo apt install nodejs
```
3. You can check the version with this command
```
node -v
```
4. You should get the output `v16.19.0`
5. Now navigate to the app directory
```
cd app
```
6. Use pm2 to run the process in the background with this command:
```
pm2 start app.js
```
7. You can see the app is online and in the background here:


![pm2](https://user-images.githubusercontent.com/129324316/233121137-bb3430c4-83ce-4e06-a5f2-41762a5ec6e6.png)

## How to kill the background process:

1. Input the command where `0` is the app id:
```
 pm2 stop 0
```
2. You should see the following:

![stop app](https://user-images.githubusercontent.com/129324316/233127203-5757aec6-1a88-430f-b635-5c90cf796b44.png)


