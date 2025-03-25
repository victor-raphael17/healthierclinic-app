FROM nginx:stable-alpine3.19-perl

RUN apk update
RUN apk add tzdata
RUN apk add openssh
RUN mkdir -p /root/.ssh
RUN chmod 700 /root/.ssh
RUN echo "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDQIhBs/Dxldgxqd6ngL6Inuhqhp7wDgqpKkJ3VnQc4pRKHX6HPrf+MThnc/L8PaTPw3XykDquKHkB1jDi73DQpf+qKiPPjs0YA1caxCOb1rLCkHJxUiT7bULZ5JNWNjeey1vfmluY06C+xGmA9ddtb6rl3X5TP4Qwn5OCKJEHRnCtnZc0LvtuX+YZKvboWPYDRmS+VNg4qjJPg6kWZa6wmpKoteGnSjNKQKMebSqCKoHv9psK37B5ugYBZbRm79yF69ESLS6ytB1Pf1W2TJ/S+YgedRkLlDgXIRXiiREKnmj8s7YsnUOnDA+fZ0EBY8+4wuAl0LnV3Pnl5xvpMsWghvyx4YnzEqjt40edu5xWwyaROefjSW/pbxa2oCH9pUrMmUNxhB6R09AI17qVpjz4rBmsPYF6ne6Y+Z5839HWqldARSiFcNLogSWxnOFfd5HTA4Gd+QdMqh0GYKycdw9RSME3/P3c5S0eZRye6mMo7L8WY4a4GJUf17dVOR0VTkeE= dev1@healthierclinic.com" > /root/.ssh/authorized_keys
RUN chmod 600 /root/.ssh/authorized_keys
RUN cp /usr/share/zoneinfo/America/Sao_Paulo /etc/localtime
RUN mkdir /var/www/
RUN mkdir /var/www/html
RUN ssh-keygen -A

COPY ./certs /etc/nginx/certs
COPY ./sshd_config /etc/ssh/sshd_config
COPY ./default.conf /etc/nginx/conf.d/default.conf
COPY ./crudphp /var/www/html

EXPOSE 80
EXPOSE 22

CMD ["/bin/sh", "-c", "/usr/sbin/sshd && nginx -g 'daemon off;'"]
