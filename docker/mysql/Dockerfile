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

# RUN adduser mysql mysql

RUN \
apk update && apk add \
openrc \
mysql \
mysql-client \
curl && \
mkdir -p /var/lib/mysql /var/run/mysqld && \
chown -R mysql /var/lib/mysql /run/mysqld && \
chgrp -R mysql /var/lib/mysql /run/mysqld
# EXPOSE 3306

USER mysql

# RUN mysql_install_db --user=mysql --basedir=/usr/ --ldata=/var/lib/mysql --skip-test-db
# rm -rf /var/lib/mysql/*

ENTRYPOINT mysqld_safe --user=mysql --data=/var/lib/mysql --basedir=/usr/ --skip-syslog
# ENTRYPOINT ["mysqld_safe", "--data=/var/lib/mysql", "--skip-syslog"]

# ENTRYPOINT mysqld
# CMD mysql -umysql -Bse "$SQL_SCRIPT"

# ENTRYPOINT tail -f /dev/null