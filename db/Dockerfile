FROM mysql:8.0.37-debian

RUN apt-get update
ENV TZ='America/Sao_Paulo'
RUN apt install tzdata
RUN apt-get install -y net-tools

ARG MYSQL_ROOT_PASSWORD
ENV MYSQL_ROOT_PASSWORD=${MYSQL_ROOT_PASSWORD}

COPY sqlInstructions.sql /docker-entrypoint-initdb.d/sqlInstructions.sql

EXPOSE 3306
