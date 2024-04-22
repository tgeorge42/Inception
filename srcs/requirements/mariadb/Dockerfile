FROM debian:bullseye

RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get install mariadb-server -y

RUN mkdir -p /var/run/mysqld
RUN chown -R mysql:mysql /var/run/mysqld
RUN chmod 777 /var/run/mysqld

# RUN mkdir -p /run/mysql/ && touch /run/mysqld/mysqld.sock && chmod 777 /run/mysqld/mysqld.sock

COPY conf/50-server.cnf	/etc/mysql/mariadb.conf.d/50-server.cnf
COPY tools/launch_MySQL.sh /usr/local/bin/launch_MySQL.sh
RUN chmod 777 /usr/local/bin/launch_MySQL.sh

EXPOSE 3306

CMD [ "/usr/local/bin/launch_MySQL.sh" ]
