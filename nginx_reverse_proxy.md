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
|Client sends a request |Client sends a request|
|Proxy routes the request to requested destination|Reverse proxy sends request to original server|
|The proxy then evaluates and inspects any response|This server is called the “origin server” since it’s what will actually be responding to requests.|
|Proxy takes action as needed|Reverse proxy crafts response based on data returned from the server|
|Forwards it to the originating client if appropriate|Sends response back to client|


## Nginx reverse proxy steps

1. Modify the location in the default file, using command ` sudo nano /etc/nginx/sites-available/default
2. Add the location to the file as shown, making sure you include port 3000:
```
   location / {
       proxy_pass http://192.168.10.100:3000;
       proxy_http_version 1.1;
       proxy_set_header Upgrade $http_upgrade;
       proxy_set_header Connection 'upgrade';
       proxy_set_header Host $host;
       proxy_cache_bypass $http_upgrade;
   }
   

```

3. Check for any syntax error using ` sudo nginx -t`
4. Restard nginx ` sudo systemctl restart nginx`
5. Navigate to the app directory `cd app`
6. Run `npm install`
7. Launch the app ` node app.js`
8. Check if the app is running by entering your IP into your browser
9. You should see the following page:
![sparta test app](https://user-images.githubusercontent.com/129324316/233016094-d0f3ced4-2c4f-4793-b95d-b6447bc5df13.png)

