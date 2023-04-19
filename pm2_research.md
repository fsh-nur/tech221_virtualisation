## How to run a process in the background in linux

A background process is a process/command that is started from a terminal and runs in the background, without interaction from the user.

1. To run a command in the background, add the ampersand symbol (&) at the end of the command:
```<command> &```



## How to run nodejs app as background process using pm2
- You have already run `vagrant up` and `vagrant ssh` into your app VM

1. Navigate to your app in GitBash (You should be in the linux terminal)
```cd app```
2. Install PM2 globally using the following command. To start using PM2, you need npm and Node.js installed.
```
npm install PM2@latest -g
```
3.Launch your node application using pm2
```
pm2 start app.js
```
4.
