# imitation-AWS-Mobile-server
* composition
  - Old Android Phone
  - WAS server
  - Database server
  - WEB server
  - cloudflare zero-trust
  - Domain
* Actual Use
  - VMWARE-Rocky 10.2 (WAS Server , DB Server)
  - Samsung A50(Termux)


*WAS-Install
  - sudo dnf install -y curl git net-tools
  - curl -fsSL https://rpm.nodesource.com/setup_20.x
  - sudo bash 
  - sudo dnf install -y nodejs
  - sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
  - sudo dnf install -y docker-ce docker-ce-cli containerd.io
  - sudo systemctl enable --now docker
  - mkdir ~/web-console && cd ~/web-console
    npm init -y
    npm install express socket.io ssh2 cors
  - sudo docker run -d --name cloudflared --restart unless-stopped \
  cloudflare/cloudflared:latest tunnel --no-autoupdate run --token <CLOUDFLARE_TUNNEL_TOKEN>
  
*WEB-SERVER
  - Rocky 10 install
  - add docker
  - docker run cloudflare/cloudflared:latest tunnel --no-autoupdate run --token CloudFlare_Tunnel_Token
  - docker run -d --name webs -p 8080:80 nginx:latest
  - set cloudflare Path - Domain , host path : http://localhost:8080

*phone-server
  - USE Termux
  - add Libreswan
  - add sshd


<img width="918" height="806" alt="image" src="https://github.com/user-attachments/assets/059f7f94-7f0f-4763-9b95-84c485522a0b" />

----------------------------------------------<Latest:2026.10.25>-------------------------------------------------------------
