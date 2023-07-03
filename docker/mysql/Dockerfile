FROM alpine:latest 

ENV MYSQL_DATABASE=mydb
ENV MYSQL_USER=user
ENV MYSQL_PASSWORD=pass
ENV SQL_SCRIPT="\
  CREATE DATABASE $MYSQL_DATABASE;\
  CREATE USER '$MYSQL_USER'@'%' IDENTIFIED BY '$MYSQL_PASSWORD';\
  GRANT ALL ON $MYSQL_DATABASE.* TO '$MYSQL_USER'@'%';\
  FLUSH PRIVILEGES;\
  "

RUN \
apk update && apk add \
openrc \
mysql \
mysql-client \
curl && \
mkdir -p /var/lib/mysql /var/run/mysqld && \
chown -R mysql /var/lib/mysql /run/mysqld && \
chgrp -R mysql /var/lib/mysql /run/mysqld

USER mysql

ENTRYPOINT mysqld_safe --user=mysql --data=/var/lib/mysql --basedir=/usr/ --skip-syslog
