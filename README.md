# Run self-hosted private docker registry server
[![Build Status](https://files.ariadata.co/file/ariadata_logo.png)](https://ariadata.co)

![](https://img.shields.io/github/stars/ariadata/dc-docker-registry.svg)
![](https://img.shields.io/github/watchers/ariadata/dc-docker-registry.svg)
![](https://img.shields.io/github/forks/ariadata/dc-docker-registry.svg)

> This needs : [nginx-proxy-manager with docker-compose](https://github.com/ariadata/dc-nginxproxymanager) .

---
#### 1- Install `apache2-utils` , in ubuntu :
```sh
sudo apt -y install apache2-utils
```
#### 2- Clone these repository to your system :
```sh
git clone https://github.com/ariadata/dc-docker-registry.git && cd dc-docker-registry && rm -rf .git
```
#### 3- Run docker-compose file by using :
```sh
docker-compose up -d
```
#### 4- Add first auth User/Pass by using this ( change `MY_USER`) :
```sh
htpasswd -B auth/registry.password MY_USER
```
#### 5- Goto Nginx-Proxy-Manager admin panel and add this stack as proxy-host :
> Domain : `Your-FQDN` you must pointed it before!
> 
> Schema : `http`
> 
> Name or IP : `docker-registry`
> 
> Port : `5000`
>
> Config SSL Part

#### 5- Use It! (basic example): 
```sh
docker login Your-FQDN
docker pull nginx
docker tag nginx Your-FQDN/nginx
docker push Your-FQDN/nginx
```

Done!
