FROM alpine:3.14
RUN apk update && apk add \
openrc \
mysql \
mysql-client \
curl

RUN rm -rf /etc/my.cnf /etc/mysql/* /etc/mysql.d/ && \
mkdir -p /var/lib/mysql /var/run/mysqld && \
chown -R mysql /var/lib/mysql /run/mysqld && \
chgrp -R mysql /var/lib/mysql /run/mysqld && \
mysql_install_db --user=mysql --ldata=/var/lib/mysql

EXPOSE 3306

USER mysql

ENTRYPOINT ["mysqld_safe", "--data=/var/lib/mysql", "--syslog"]