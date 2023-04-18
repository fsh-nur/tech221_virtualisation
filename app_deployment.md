# Deploying the sparta app using vagrant

## Download app.zip and environment.zip

1. Make sure the files are unzipped in the vagrant directory.
2. Input the following into your vagrantfile in order to sync the vagrant file with the app:

```
  config.vm.synced_folder "app", "/home/vagrant/app"

```

![How your page should look](https://user-images.githubusercontent.com/129324316/232790049-2c02243e-105e-4d80-be89-0e8010b771d1.png)

3. In order to check if the app is in the directory:
    -- run `vagrant up` in the terminal
    -- run `vagrant ssh` in GitBash (this will open the linux terminal)
    -- run `ls`
    -- app should be present
    
![App is in th efolder](https://user-images.githubusercontent.com/129324316/232793149-9905b9bc-e226-4f14-b20b-0844d9f193f7.png)

4. Now we run the tests to see if everything is installed that should be installed. 
   -- cd into /environment in VSCode terminal
   -- cd into environment again if it is nested
   -- cd into /spec-tests
   -- input `gem install bundler`
   -- input `bundle` to bundle up the tests
   -- input `rake spec`
   -- everything that is not installed will show up
   
5.  Now we install what we are missing (nginx should already be installed- check automation.md)
6. In GitBash install nodejs  `sudo apt-get install nodejs -y`
7. Install python software package which adds new software repositories to a system's package source. `sudo apt-get install python-software-properties`
8. Install the version 6 of nodejs `curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -g` the input `sudo apt-get install nodejs -y`
9. In order to make sure this is the correct version input `nodejs --version`
10.  Install pm2 package manager for nodejs `sudo npm install pm2 -g`
11.  In order to run our app we must install nodejs package dependencies.
     -- cd into our app on GitBash `cd app`
     -- input `npm install`
     -- input `node app.js`

![app 3000](https://user-images.githubusercontent.com/129324316/232798838-51a0d0fd-acfc-4e53-a6eb-2c782eaaa2ed.png)

12. Go to 192.168.10.100:3000 and you should see:
 ![sparta test app](https://user-images.githubusercontent.com/129324316/232799026-77103e0b-f70f-4dfe-b1dd-095e5d64c3e7.png)
