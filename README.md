This PHP/CRUD application was created for educational purposes only. The original PHP code can be found at "https://codeshack.io/crud-application-php-pdo-mysql/#packages".

## How to Run
1. Update your package lists
    - sudo apt update -y

3. Upgrade your packages
    - sudo apt upgrade -y
    
5. Install Docker engine and run the hello-world test
    - https://docs.docker.com/engine/install/
      
6. Add user to docker group, using append and refresh the group
    - sudo usermod -aG docker ubuntu
    - newgrp docker
      
7. Create the docker subnet that bind and the app will use (they're setted to use 172.19.0.0/24 range)
    - docker network create --subnet=172.19.0.0/24 mysharednet
      
8. Clone this project infraesctructure github repository. You will need this to launch your DNS server, so the containers can find one another)
    - https://github.com/victor-raphael17/healthierclinic-infra.git
      
9. Go to 'healthierclinic-infra/bind'
    - cd healthierclinic-infra

10. Edit the "environment" and the "port" sections, adjusting it to your own IPv4 and the right timezone
10.1. You can check your IPv4 running "ip -c -br a" this will guarantee a brief and colorful output, making easy to you identify the IP. If you're using wifi, look for something like "wlp0s" and if you're using wired connection, look for something like "eth0", "enp" or "ens33"

11. Executar o docker compose (docker compose up -d)
13. Após isso, o site já estará disponível para acessar por meio do navegador
