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

## Monolithic Architecture vs 2-tier Architecture vs Microservices

- The most basic form of architecture is **monolithic architecture**, this is where all work is done on one server, and all software and applications are run on one single server. You can imagine that there is a lot of risk when it comes to this as if the server crashes, it will be very difficult to recover any work.

- As a DevOps team, **2-tier architecture** is adopted instead which is more reliable. This is made up of an app and a database, which support each other, where if one of them is down, the other can be recovered.

- **Microservices architecture** is seen as even better as it is broken down into smaller pieces so it becomes more robust.
