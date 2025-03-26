# Healthierclinic

A Dockerized Nginx, PHP, and MySQL CRUD application.

This PHP CRUD application was created for educational purposes. The original PHP code can be found [here](https://codeshack.io/crud-application-php-pdo-mysql/#packages).

## How to Run

### 1. Update your package lists
``` sudo apt update -y ```

### 2. Upgrade your packages
``` sudo apt upgrade -y ```

### 3. Install Docker Engine and run the hello-world test
      - [Install Docker Engine](https://docs.docker.com/engine/install/)
      
### 4. Add your user to docker group using append and then refresh the group
sudo usermod -aG docker ubuntu**
    - **newgrp docker**
      
6. Create the docker subnet that bind and the app will use (they're setted to use 172.19.0.0/24 range)
    - **docker network create --subnet=172.19.0.0/22 mysharednet**
      
7. Clone this project repository
    - **git clone https://github.com/victor-raphael17/healthierclinic-app.git**
      
14. Make the **.env** file in the **healthierclinic-app/db** directory and set the **MYSQL_ROOT_PASSWORD** variable

14. Run the composer file
     - **docker compose up -d**
       
15. Now you can access the application through your IPv4, it's running on 80 port
   
15. Run compose down to stop the project
     - **docker compose down**
