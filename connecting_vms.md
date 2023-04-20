## Connecting our db vm to our app vm

1. Make sure to change the ubuntu to bionic in `db` and `app` respectively
```
    app.vm.box = "ubuntu/bionic64"

```
```
    db.vm.box = "ubuntu/bionic64"

```
2. Log into your virtual machines in 2 different terminals in GitBash

```
vagrant ssh db
```
```
vagrant ssh app
```
3. Check you have everything you need -- node, --pm2. --app
```
cd app
node --version
pm2 --version
```
4. Change configuration of MongoDB
```
sudo nano /etc/mongod.conf
```
5.  Scroll down in the file until you see this:
![network interfaces](https://user-images.githubusercontent.com/129324316/233341706-e3e2876d-f362-4cc1-8629-d0dd20b80e0f.png)

7. Change the network IP to: 0.0.0.0

8. Now we restart in order to run it with the changes

```
sudo systemctl restart mongod
```
9.  We also enable MongoDB to check the changes are set and check the status :

```
sudo systemctl enable mongod
```

![mongo active](https://user-images.githubusercontent.com/129324316/233389685-f2be191c-5196-4116-9ca5-f1b104084a2a.png)

10. Now onto the `app` virtual machine:
11. In GitBash we can use an environment variable in our bashrc, by opening it

```
sudo nano .bashrc
```
12. We have to tell our virtual machine where it will be connecting to - input an environment variable referenced by developers for nodejs app. Input the following in our .bashrc to allow us to connect to the database by inputting the db IP and MongoDB's port

```
export DB_HOST=mongodb://192.168.10.150:27017/posts
```
13. Now exit by using `CTR+X` and `yes`
14. Refresh the page using this command:
```
source .bashrc
```
15. Now if you input this command you should see the environment variable you put in
```
printenv DB_HOST
```

![db host](https://user-images.githubusercontent.com/129324316/233395648-119b3b32-7dcb-4e23-8a06-88620c8c9ece.png)

17. Navigate to the app
```
cd app
```

18. Install the application
```
npm install
```
19. Run a file that the developers have written that seeds the data into mongoDB
```
node seeds/seed.js
```
20. The database should be seeded if successful 

![db seed](https://user-images.githubusercontent.com/129324316/233398891-358dffa4-2dd4-4217-9a4e-11ef9afb0c5c.png)

21. Now to start our app 
```
node app.js
```
22. Now if you input the IP address into your web browser : 192.168.10.100:3000/posts you should see the following page



![posts](https://user-images.githubusercontent.com/129324316/233399621-d4c3d826-f3a5-4bc7-9d28-d4409cae7cc7.png)
