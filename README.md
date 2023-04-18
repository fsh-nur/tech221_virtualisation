# Virtualisation

## What is a virtual machine?
A virtual machine is emulated equivalent of a computer system that runs on top of another system.
![Ease of Use (3)](https://user-images.githubusercontent.com/129324316/232559134-60a96d95-171f-4431-90c4-430dfea0f46d.png)

## What is a dev environment?
A dev environment is a virtual machine workspace which runs in the cloud or a local data center, where can run software outside of our local machine. They are useful to developers as they can create and innovate applications without breaking something in a live environment.

 ## The 4 Important Areas of DevOps
![Ease of Use](https://user-images.githubusercontent.com/129324316/232518794-30e83636-ce14-483e-8d99-f7a23e91d8f1.png)

—Cost

- We need to make sure that companies are being as efficient as possible
- Cost is often overlooked can we get a more basic package
- For example scaling how powerful a machine do we need

—Flexibility

- Being aware of vendor lock-in
- Being flexible when it comes to the tools we need
- Everything the company uses should be easily transferred to another software/tool

—Ease of Use

- Making things as easy as possible for developers to do their job and use.
- If devs do not use our tools there will be headaches down the line.

—Robustness

- We need as close to 100% uptime of our services as possible.

## What makes a good DevOps Environment?

![Ease of Use (2)](https://user-images.githubusercontent.com/129324316/232559340-41c2ab79-7d7c-480c-b457-85b6fb9e6f94.png)

- User friendly, fast and robust: Dev environments doing dev work in our environment instead
- Dev environment should be as close to the production environment as possible, so you can catch errors in the dev environment before it gets to the production environment.
- It should support one application only: Different apps may require different versions of a software, there may be conflicts such as different apps.
- It should be the same for everyone everywhere to avoid conflicts
- It should be easy to update


## Vagrant Cheatsheet

Common commands:

     autocomplete    manages autocomplete installation on host
     
     box             manages boxes: installation, removal, etc.
     
     cloud           manages everything related to Vagrant Cloud
     
     destroy         stops and deletes all traces of the vagrant machine
     
     global-status   outputs status Vagrant environments for this user
     
     halt            stops the vagrant machine
     
     help            shows the help for a subcommand
     
     init            initializes a new Vagrant environment by creating a Vagrantfile
     
     login
     
     package         packages a running vagrant environment into a box
     
     plugin          manages plugins: install, uninstall, update, etc.
     
     port            displays information about guest port mappings
     
     powershell      connects to machine via powershell remoting
     
     provision       provisions the vagrant machine
     
     push            deploys code in this environment to a configured destination
     
     rdp             connects to machine via RDP
     
     reload          restarts vagrant machine, loads new Vagrantfile configuration
     
     resume          resume a suspended vagrant machine
     
     serve           start Vagrant server
     
     snapshot        manages snapshots: saving, restoring, etc.
     
     ssh             connects to machine via SSH
     
     ssh-config      outputs 
     
     OpenSSH valid configuration to connect to the machine
     
     status          outputs status of the vagrant machine
     
     suspend         suspends the machine
     
     up              starts and provisions the vagrant environment
     
     upload          upload to machine via communicator
     
     validate        validates the Vagrantfile
     
     version         prints current and latest Vagrant version
     
     winrm           executes commands on a machine 
     via WinRM
     
     winrm-config    outputs WinRM configuration to connect to the machine

For help on any individual command run `vagrant COMMAND -h`

Additional subcommands are available, but are either more advanced
or not commonly used. To see all subcommands, run the command

`vagrant list-commands`.
        --[no-]color                 Enable or disable color output
        --machine-readable           Enable machine readable output

    -v, --version                    Display Vagrant version
        --debug                      Enable debug output
        --timestamp                  Enable timestamps on log output
        --debug-timestamp            Enable debug output with timestamps
        --no-tty                     Enable non-interactive output
        
        

