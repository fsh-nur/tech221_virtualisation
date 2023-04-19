# Reverse Proxy

## Ports

Ports in a computer system is the communication and connection between a local machine and a network. Ports are manageed my a computer's operating system and arsoftware based. Each port is associated wit specific task.Each port is assigned a number and are standardized aross all network-connected devices.
Examples of ports include:
- Port 22: SSH secure network connection
- Port 80: HTTP connection making the World Wide Web possible
- Port 500: Setting up a secure IPsec connection.

## What is a proxy and what is a reverse proxy?

A proxy is a server that is in front of a client machine, where request from the client machine go through a proxy which communicates with the web server on behalf of them.
There are forward proxies and reverse proxies.A reverse proxy is a server that forwards a request from a client to another server and returns the results from the server that actually processed the request to the client as if the proxy server had processed the request itself. A forward proxy is used by a client, while a reverse proxy is used by an internet server.

| Forward Proxy | Reverse Proxy |
| :------------ | ------------: |
| ![Forward Proxy](https://user-images.githubusercontent.com/129324316/233011461-0830e2f8-f215-49ae-91b2-5741de06d861.png)|![Forward Proxy (1)](https://user-images.githubusercontent.com/129324316/233011758-1138e6f3-9100-4fa2-978b-1dbb258cac9e.png)               |
| It evaluates client requests, |Instead of connecting directly to a website serving content|
|takes any needed actions, and routes the request to the destination on the client’s behalf.|a reverse proxy like NGINX can sit in the middle. When it receives a request from a user, it will send forward, or “proxy,” that request to the final server.|
|The proxy then evaluates and inspects any response,|  This server is called the “origin server” since it’s what will actually be responding to requests.|
|takes action as needed,||
|forwards it to the originating client if appropriate||
