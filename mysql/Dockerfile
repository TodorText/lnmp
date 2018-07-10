ARG MYSQL_VERSION=5.7
FROM mysql:${MYSQL_VERSION}

MAINTAINER Mahmoud Zalt <mahmoud@zalt.me>

#####################################
# Set Timezone
#####################################

ARG TZ=UTC
ENV TZ ${TZ}
# windos获取不到,删除第一行即可
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime  \
&& echo $TZ > /etc/timezone \
&& chown -R mysql:root /var/lib/mysql/ \
&& mkdir /etc/mysql/data \

ADD my.cnf /etc/mysql/conf.d/my.cnf
CMD ["mysqld"]

EXPOSE 3306
