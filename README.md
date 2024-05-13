#### 
Create a Project Directory
####
    mkdir /root/nginxproxy
#### 
    version: '3.8'
    services:
      app:
        image: 'jc21/nginx-proxy-manager:latest'
        restart: unless-stopped
        ports:
          - '90:80'
          - '91:81'
          - '443:443'
        volumes:
          - /root/nginxproxy/data:/data
          - /root/nginxproxy/letsencrypt:/etc/letsencrypt

####
    docker-compose up -d
