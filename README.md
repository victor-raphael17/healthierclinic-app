This PHP/CRUD application was created for educational purposes only. The original PHP code can be found at "https://codeshack.io/crud-application-php-pdo-mysql/#packages".

## How to Run
1. Update your package lists
    - sudo apt update -y

3. Upgrade your packages
    - sudo apt upgrade -y
      
4. Install Docker Engine and run the hello-world test
    - https://docs.docker.com/engine/install/
      
5. Add user to docker group, using append and refresh the group
    - sudo usermod -aG docker ubuntu
    - newgrp docker
      
6. Create the docker subnet that bind and the app will use (they're setted to use 172.19.0.0/24 range)
    - docker network create --subnet=172.19.0.0/22 mysharednet
      
7. Clone this project repository
    - git clone https://github.com/victor-raphael17/healthierclinic-app.git
      
8. Go to 'healthierclinic-app/bind'
    - cd healthierclinic-app/bind

10. Edit the docker compose file.
    Adjust the environment variables and the ports section to match your IPv4 and the correct timezone. You can check your IPv4 by running "ip -c -br a", this will guarantee a brief and colorful 
    output, making it easy to you identify the IP.
    If you're using wifi, look for something like "wlp0s" and if you're on wired connection, look for something like "eth0", "enp" or "ens33".

12. If your IP starts with "192.168" the bind configuration is fine. If doesn't, then you'll need to change the "acl internal" directive, located at bind/config/named.conf, to match with yours.

13. Run the bind container. After this step, you should see the bind container running continously, without crashing or anything like that.
     - docker compose up -d

14. Go back to healthierclinic-app
     - cd ..

15. Run the composer file
     - docker compose up -d
   
16. Run compose down to stop the project
     - docker compose down

17. To purge every data you downloaded, delete the project directory and run "docker system prune"
